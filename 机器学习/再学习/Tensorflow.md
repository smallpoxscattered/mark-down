---
typora-root-url: 机器学习\tenserflow
---

## Tensorflow

### 基本概念

**计算图**

~~~~~
是一个有向图，也称作数据流图
在计算图中，节点表示计算单元，边表示计算使用或产生的数据

同时也分静态计算图和动态计算图
~~~~~

**会话(Session)**

~~~~~~
是客户端程序和TensorFlow系统交互的接口
同时，计算图必须在会话中执行 --> 用Extend方法添加节点，tf.Session的run方法执行计算图
TensorFlow2.0默认动态计算图，但也提供了tf.function方法
~~~~~~

**运算操作和运算核**

~~~~~~~
运算图中的每一个节点都是运算操作(Operation,简称Op)，同时每一个运算操作都有自己的名称
运算操作也能拥有自己的属性，但必须提前设置，例如，让向量加法操作只接受浮点类型的张量

运算核(Kernel)是一个运算操作在某一个具体硬件(比如CPU或GPU)上实现
~~~~~~~

部分运算操作

![qq_pic_merged_1667372452562](/../../qq_pic_merged_1667372452562.jpg)

**张量(Tensor)**

~~~~~
张量可以看作一个多维的数组或列表

张量具有两种属性
1.数据类型 （同一个张量中，元素类型相同）
2.形状（张量的维数和每个维度的大小）
~~~~~

张量形状图

![qq_pic_merged_1667372675863](/../../qq_pic_merged_1667372675863.jpg)

特殊的张量

~~~~~
tf.variable:变量
	变量是可以持续保存并被修改(assign和assign_add)的张量，但维度不可以被修改
tf.constant:常量
	常量定义必须初始化，值和维度都不可变
tf.placeholder:占位符
	TensorFlow2.0已不再使用
tf.SparseTensor：稀疏张量
~~~~~

**1.x到2.0变化**

~~~~~~
1.API精简
2.动态计算图变为默认
3.取消全局变量，转为跟踪变量
4.使用函数而不是会话
	使用tf.function()修饰python并标记即时编译，使得TensorFlow可以将其作为单个图执行
~~~~~~

### 基本框架

![qq_pic_merged_1667370624969](/../../qq_pic_merged_1667370624969.jpg)

**流程**

~~~~~~~~
1.使用tf.data创建输入管道来读取训练数据，并通过tf.feature_column来指定特征列或交叉特征

2.使用tf.keras 或 Premade Estimators构建、训练和验证模型

3.使用Eager Execution运行和调试模型，以及使用tf.function充分利用计算图的优势
	Eager Execution模式下，可以更加方便地编写和调试代码，在TensorFlow2.0中默认开启
	可以用tf.function将python程序转为TensorFlow地静态计算图

4.使用Distribution strategies进行分布式训练
	将训练任务分配到单节点，多加速器及多节点或多加速器

5.使用SavedModel储存模型
	有两种模型储存格式:一个是检查点（Checkpoints），另一个是SavedModel
	前者以来创建模型地源代码，后者则与此无关
~~~~~~~~

### 代码实现

#### tf.data  API

**介绍**

~~~~~~~
除了GPU和TPU等硬件加速设备外，高效的数据输入管道也可以很程度提升模型性能

数据输入管道的本质是ELT（Extract、Transform 和 Load）的过程
	Extract：从硬盘中读取数据（可以是本地，也可以是云端）
	Transform：数据的预处理（数据清洗、格式转换等）
	Load:将处理好的数据加载到计算设备（例如CPU、GPU及TPU等）
~~~~~~~

**图像处理函数**

~~~~~~~~
def load_and_preprocess_image(path):
    # 读取图片
    image = tf.io.read_file(path)
    #jepg图片解码，得到一个三维的张量
    image = tf.image.decode_jpeg(image, channels=3)
    #每张照片的大小不同，统一成192*192
    image = tf.image.resize(image, [192, 192])
    # 归一化处理  或者其他的 图像处理的方法
    image = image / 255.0
    
    return image
~~~~~~~~

基于图像的多分类问题,所以图片类型只用train,而没有对应的图片label，对应的构造函数

~~~~~
def load_and_preprocess_image(path):
    
    # 读取图片
    image = tf.io.read_file(path[0])
    image = tf.image.decode_jpeg(image, channels=3)
    image = tf.image.resize(image, [192, 192])

    label = tf.io.read_file(path[1])
    label = tf.image.decode_jpeg(label, channels=1)
    label = tf.image.resize(label, [192, 192])
    # 归一化处理  或者其他的 图像处理的方法
    image = image / 255.0
    label = label / 255.0
    
    return image,label
~~~~~

**构建输送管道**

不要尝试将构造数据管道的代码封装成函数,以便快速构造两者, 经过试验会出现内存爆满,进程被杀死的情况

~~~~
# 创建 图片文件 路径的 管道的结点 图片路径的数据集
path_ds = tf.data.Dataset.from_tensor_slices(all_image_paths)
# 使用 AUTOTUNE 自动调节管道的参数
AUTOTUNE = tf.data.experimental.AUTOTUNE
# 构建图片的数据集
image_ds = path_ds.map(load_and_preprocess_image,num_parallel_calls = AUTOTUNE)
# 构建图片 类标数据 的数据集
label_ds = tf.data.Dataset.from_tensor_slices(tf.cast(all_image_labels, tf.int64))
# 将图片 和 类标 压缩为(图片, 类标)对
image_labels_ds = tf.data.Dataset.zip((image_ds, label_ds))
#打乱数据集
image_labels_ds = image_labels_ds.shuffle(buffer_size=3670)
#里面的数据可以被重复使用两遍
image_labels_ds = image_labels_ds.repeat(2)
#将数据合成8个为一组
image_labels_ds = image_labels_ds.batch(8)
让模型的训练和每个批次数据的加载并行
image_labels_ds = image_labels_ds.prefetch(buffer_size = AUTOTUNE)
~~~~

代码解析

~~~~~
创建图片路径的数据集，使用tf.data.Dataset中from_tensor_slices方法使用切片元素构建数据集，还有from_tensor，直接使用单个张量来构建数据集，以及from_generator方法使用生成器构建数据集

map在这里类似apply函数，将里面的元素依次用函数处理，且结果数据顺序不变

zip方法，将图像数据和类标数据压缩成(图片，类标)对

repeat(x)方法可以让数据可以被重复使用x遍，不加参数可以无限次重复获取数据

prefetch方法可以让ELT过程中的数据准备和预处理（EL）和数据消耗（T）过程并行
~~~~~

**映射**

~~~~~~~~~
我们前面归一化后的数据范围是[0,1]，而不同的模型接受参数的范围不同

转[-1,1] : [0,1]*2 - 1
转[0.01,0.9] : [0,1]*0.89 + 0.01

总结，先利用乘法改变范围，再利用加减法，移动范围位置
~~~~~~~~~







## pathlib

~~~~~~
用于处理文件系统路径的类
~~~~~~

**导入包**

~~~~~
form pathlib import Path
~~~~~

**列出根目录**

~~~~~
root = Path.cwd()
~~~~~

**列出目录下符合的文件**

~~~~~~
file = list(root.glob('*/*/*'))

由于里面的元素类型是  <class 'pathlib.WindowsPath'>
所以可以转化为字符串
file = [f"{x}" for x in file]
f"{x}"可以替换成str(x)

读取文件名，只提取文件夹，并排序
file = sorted(item.name for item in file if item.is_dir())
~~~~~~

**查询路径属性**

~~~   
path.exists()   判断是否存在
path.is_dir()   判断是否是文件夹
path.is_file()  判断是否是文件
path.is_absolute()判断是否是绝对路径
~~~

**迭代器**

~~~~~~~
当path为文件夹的时候，通过yield产生path文件夹下的所有文件、文件夹路径的迭代器
root = Path.cwd()
for i in root.iterdir()
	print(i)
~~~~~~~

**读取文件**

~~~~~~
Path.open() 和 open()相似
~~~~~~

