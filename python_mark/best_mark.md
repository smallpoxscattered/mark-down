---
typora-root-url: python_mark
---

### 电脑			

#### 安装程序

1. 非c盘    2.新建   3.非英文  4.安装

#### 卸载程序

1. 控制面板  2.程序和功能  3.卸载

工具typora   语法markdown

#### markdown

1. 标题 
   + “#”+空格且“#”越多则字体越小
   + 快捷方式：ctrl+数字

2. 目录 :[toc]+回车（一定要英文）
3. 列表
   + 有序：数字+点+空格
   + 无序：“+”或“-”+空格

4. 表格：ctrl+t
5. 斜体：星星+”字“+星星   星星：*
6. 加粗：两个星星+”字“+两个星星
7. 斜体+加粗：三个星星+”字“+三个星星
8. 编码（白色区域）：~~~+”python“

#### 文件路径

1. 绝对路径 (全部的地址)
2. 相对路径 (后面的地址)
   - "."和“./”   是当前属找种差
   - “../”   是上一级属

## python基本知识

##### python运行形式

1. 交互式  cmd==》python  （不能保存)
2. 文件形式（文件后缀：py）等效于python+文件路径（永久保存）

~~~python
隐私文件可以改变后缀来隐藏
~~~

##### 寻找python

1. cmd==》where python
2. 环境变量

##### 注释

1. ”# “           						 单行注释    (快捷键：ctrl + /)
2. ''' '''  或""" """                    多行注释

~~~python
用“TODO”  来标识提醒自己
~~~

##### 快捷方式

1. ctrl+d            快速复制当行
2. ctrl+y            删除当行
3. ctrl+c            复制
4. ctrl+v            粘贴
5. ctrl+z            回退
6. ctrl+x            剪切
7. ctrl+a            全选
8. ctrl+s            保存文件
9. ctrl+tab        切换软件页面

##### 变量

变量含义

- 计算机中数据的ip地址

赋值含义

- 将数据放入变量

~~~~~~~~~
python中的赋值转牛角尖
https://www.cnblogs.com/kiko0o0/p/8135184.html
(里面还有浅拷贝和深拷贝)
~~~~~~~~~



##### 标识符

- 由数字、字母、下划线组成
- 不能以数字开头
- 不能使用内置关键字
- 严格区分大小写

##### 命名规范

- 驼峰命名法：大驼峰命名法和小驼峰命名法
  - 大驼峰：第一个单词的首字母都采用大写    例：MyName
  - 小驼峰：第一个单词以小写字母开始；第二个单词的首字母大写  例：myName

- 使用下划线   例子:print_number

##### 关键字

~~~python
import keyword
print(keyword.kwlist)

['False', 'None', 'True', 'and', 'as', 'assert', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']

不能以上面这些关键字来命名
~~~

##### 数据类型

数值类型

1. 整数类型：int
2. 浮点类型：float    （指数形式aen或aEn）（指数形式最后结果一定是浮点数）
3. 布尔：bool   [Ture 和False(注意大小写) ，前者为1，后者为0]

序列类型

1. str 字符串
2. list 列表
3. tuple 元组
4. dict 字典
5. set 集合

~~~~
序列分为可变和不可变，评判标准是当其值改变时，若其内存地址不变则为可变序列，若内存地址变，则为不可变序列
~~~~

散列类型

1.集合

##### 查看数据特征

- 查看数据类型：type()
- 查看数据地址：id()
- 查看数据的值：values()
- 查看数据的键:   keys()

##### 转义字符 \ （必须在引号内使用)

1. 内涵：将字符编程纯文本
2. 常用
   - \n表示换行
   - \t相当于tab，四个空格
   - 两个\相当于\

##### 类型转换

| 函 数                 | 作 用                                            |
| --------------------- | ------------------------------------------------ |
| int(x)                | 将 x 转换成整数类型                              |
| float(x)              | 将 x 转换成浮点数类型                            |
| complex(real,[,imag]) | 创建一个复数                                     |
| str(x)                | 将 x 转换为字符串                                |
| repr(x)               | 将 x 转换为表达式字符串                          |
| eval(str)             | 计算在字符串中的有效python表达式，并返回一个对象 |
| chr(x)                | 将整数 x 转换为一个字符                          |
| ord(x)                | 将一个字符 x 转换为它对应的整数值                |
| hex(x)                | 将一个整数 x 转换为一个十六进制字符串            |
| oct(x)                | 将一个整数 x 转换为一个八进制的字符串            |



##### 输入和输出

输入 input()

~~~~~
1.input() 返回值是字符串类型
2.input() 里面可以放数据，用来提示输入者
~~~~~

输出 print()

~~~~~~
1.print()默认end='\n'
2.逗号为分隔符，输出时，以空格形式输出
3.+号在字符串中是拼接，在数字中是加法
~~~~~~

##### 运算符

算术运算符 

~~~python
+，-，*，/(除出来是一个浮点数)，%(取余数),**9(幂指数)，//(取整数)，()小括号
~~~

比较运算符

| 运算符 | 描述                             | 实例                |
| ------ | -------------------------------- | ------------------- |
| ==     | 等于 -- 比较对象是否相等         | (a == b) 返回 False |
| !=     | 不等于--比较两个对象是否不相等   | (a != b) 返回 True  |
| >      | 大于--返回x是否大于y             | (a > b) 返回 False  |
| <      | 小于--返回x是否小于y             | (a < b) 返回True    |
| >=     | 大于或者等于--返回x是否大于等于y | (a >= b) 返回 False |
| <=     | 小于或者等于--返回x是否小于等于y | (a <= b) 返回 True  |

赋值运算符

~~~python
=，+=，-=，*=，/=，%=，**=
~~~

逻辑运算符

~~~python
p为真命题，q为假命题。
and，or，not(全部为小写)
~~~

| 逻辑运算符 | 含义 | 基本格式 |
| ---------- | ---- | -------- |
| and        | 且   | a and b  |
| or         | 或   | a or b   |
| not        | 非   | not a    |

成员运算符

~~~python
in，not in(用于判断是否再序列中，返回Ture或者False)
~~~

身份运算符

~~~python
is，is not(用于比较两个对象的存储单元，由于在python中，由值来决定储存单元，所以is则是判断两个值是否相等与==作用相同，但后者只局限于数值类型)
~~~

运算优先级

- 算术运算符大于比较运算符
- 比较运算符大于逻辑运算符
- 逻辑运算符中not>and>or

## python核心进阶

#### 流程控制语句

##### 流程图

~~~~wangdefa
非常重要，相当于力学中的受力分析，电学中的电路分析
~~~~

##### if

缩进

~~~~
python中用缩进来表示语句的开始和退出
用四个空格或者一个tab表示一个缩进(缩进不对会报错)
~~~~

if格式  (if作为条件语句，用于分列不同条件)

~~~~
- if......else （两种条件）
- if...elif....elif...else  （多种条件）
~~~~

三目运算符(用于简单的代码)

~~~~
简洁写法  两个数字中取更大的数字  三行简洁形式
a = int(input('a数字的大小'))
b = int(input('b数字的大小'))
print(a if a > b else b)
~~~~

关键词pass

##### 循环结构

1.while

while和if，两者语法类似

~~~~
if 条件表达式
	代码块

while 条件表达式
	代码块
~~~~

while...else

~~~~
前面的while执行完后，就会执行else
~~~~

2.for循环

语法

~~~~
for 变量名 in range(start,stop,step)或者字符串:
    循环体
~~~~

range()注意

~~~~
1.左闭右开
2.接收的参数必须是整数
3.是不可变的序列类型
start默认为0
stop无默认
step 默认为1，不可为0
只填一个数字则默认为stop
~~~~

3.break 和 continue

用法

~~~~~
break 和 continue是循环中满足一定条件中推出循环的两种方式

即在循环之中要与if搭配使用
~~~~~

区别

~~~~
break：退出整个循环
continue：退出本次循环，进行下一循环
~~~~

##### 嵌套

~~~~
也就是循环之中有循环，条件之中有条件
~~~~



### 数据类型进阶

##### 数据类型

基本数据类型分为三类：数值类型、序列类型、散列类型

##### 可变类型和不可变类型

不可变类型：数字、字符串、元组

可变类型：列表、字典、集合

### 字符串内置功能

~~~~
通用语法：
字符串名.方法名()
~~~~

#### 对于字符串的查找

##### 通过值查找索引

~~~~
find()   （找不到则返回-1）
字符串名.find(str,beg=0,end=len(string))
str——》指定检索的字符串
beg——》开始的索引，默认为0
end——》结束索引，默认为字符串的长度
~~~~

~~~~
index()  （语法和find()相同，但找不到则报错）找出第一个匹配的索引
~~~~

##### 通过索引来找值 ——切片

~~~~
切片如果超出长度也不会报错
~~~~

语法

~~~~
第一种取单个值：字符串[索引]
~~~~

~~~~
第二种取多个值：字符串[start:end:step]
step可以取负数
~~~~

##### 获取字符串长度和出现次数

len()

~~~~~~~~
语法特殊：len(字符串)
~~~~~~~~

count()

~~~~~
字符串.count(字符串)    没有则返回0
~~~~~

#### 对于字符串的修改

##### 字符串的拆分

split()       *切分字符串，返回列表形式*

语法

~~~~~
str.split(sep.maxsplit)
sep为分隔符
maxsplit为最大分割次数
~~~~~

##### 字符串的拼接

内置功能中

join()  语法

~~~~~~~
str.join(iterable)  里面的数据必须全部是字符串
~~~~~~~

非内置功能中

~~~~
通过'+'或者','来拼接
~~~~

~~~~~~
字符串格式化
~~~~~~

##### 字符串的替换

replace()

~~~~~~~~~
str.replace(old,new,max)
~~~~~~~~~



##### 去除首尾特殊字符

strip()  

 *若不指定去除字符串两边的空格、换行符、制表符，得到一个新的字符串*

~~~
str.strip('可标注的特殊字符')
~~~

##### 大小写

lower()

~~~
str.lower()
~~~

upper()

~~~~~~
str.upper()
~~~~~~

#### 对于字符串的内容判断

##### 判断开头和结尾

startwith()

~~~~~~~
str.startwith(字符串)
~~~~~~~

endswith()

~~~~~~
str.endswith()
~~~~~~

##### 判断是否是数字组成

isdigit()

~~~~~
str.isdigit()
~~~~~

### 列表list() (返回值列表)

#### 列表的增删查改

##### 增

~~~~
1.append：增添一个数据到列表最后一位
  语法：列表名.append(内容)
2.insert:添加一个数据到指定位置
  语法：列表名.insert(索引，内容)
3.extend：添加一个序列类型到最后一位且拆分序列类型
  语法：列表名.extend(序列类型)
~~~~

##### 删

~~~~~~~
1.pop：通过索引删值，默认从最后一个开始
  语法：列表名.pop(索引)
2.remove：直接删值，如有多个。删除第一个
  语法：列表名.remove(值)
3.clear：清空列表里面所有数据
  语法：列表名.clear()
4.del：全局删除或删除一个变量
  语法：del 列表名  或  del 列表名[索引]
~~~~~~~

##### 查

~~~~~~
1.切片
2.index
3.count
~~~~~~

##### 改

~~~~~
1.单个修改：通过索引修改
  语法：列表名[索引] = 内容
2.多个修改：通过切片方式  (左闭右开)
  语法：列表名[start:end] = 数据1，数据2...
~~~~~

#### 排序 sort和sorted

两者区别

~~~~
sort是在原列表上修改
sorted是返回一个新列表
~~~~

语法

sort

~~~~~~~~
列表名.sort()-->升序
列表名.sort(reverse=Ture)-->降序
~~~~~~~~

sorted

~~~~~~
li1 = sorted(li)  生成新的列表，返回值就是新列表
~~~~~~

#### 列表生成式

举个例子

生成从1到10的列表

~~~~~~
print([i for i in range(1,10)])
~~~~~~

### 元组tuple()  (返回值元组)

~~~~
1.不可变
2.占用空间小
3.不需小括号，重点在逗号
~~~~

#### 用法

~~~~~~
1.相加，两个元组相加获取生成一个新元组
2.相乘，元组*整形，将元组中的元素再创建n份并生成一个新的元组
3.获取长度
4.索引
5.切片
6.步长，隔多少取值
7.for循环  (目前只有str,list ,tuple可以被for循环)
  t = (...)
  for i in t :
      print(i)
~~~~~~

其用法很多和列表相同

#### 格式化输出

##### 用途

~~~~~~~~~
更加便利输出字符串
~~~~~~~~~

##### %方法(占位符)

常用占位符

~~~~~
1.%s = 字符串
2.%d = 整形  默认切除小数点
3.%f = 浮点型  默认小数点6位数
  %.nf-->保留n位小数点
~~~~~

语法

~~~~~~~~
'...%s%d%f...'%(str,int,float) # 一 一 对 应
~~~~~~~~

##### format()方法

语法

~~~~~
'...{}...'.format(变量)

自定义数据
即大括号里面加数字来与后面的变量对应
~~~~~

##### f-format

语法

~~~~~~
1.f"...{变量}..."
2.可以对变量进行操作
  f'...{变量-1}...'
~~~~~~

### 字典dict() (返回值字典)

语法

~~~~~
key：value-->(键:值)
~~~~~

特征

~~~~~
1.无序   2.键:不重复   3.值:可变性
~~~~~

程序对于字典的操作是基于key

~~~~~
1.通过key访问value
  print(字典[key])
2.通过key添加key-value
  字典 = {key:value}
  字典[key]=value
3.通过key删除key-value
  del 字典[key]
4.通过key修改key-value
  字典[key] = value
5.通过key判断指定key-value存否
  key in 字典
~~~~~

字典常用方法

~~~~~~
1.clear()清空键值对
  语法:字典.clear()
2.get() 获取value的常用方法
  语法:字典.get(key) 返回值为value
  直接访问不存在的key时会报错，而用get()访问不存在的key时，会返回None
3.update() 使用新的字典更新已有字典
  语法:字典.update(新字典) (返回值为None)
4.items(),keys(),values()来获取所有的键值对，key，value
  语法:字典.items/keys()/values() (返回值都是列表，其中items()返回值是[(key,value),(key,value)......])
  若要调用可以放在tuple(),list(),set()中
5.pop()  
  语法:字典.pop(key) (返回值value)
6.setdefault()
  语法:字典.setdefault(key,value)  (返回值value)
  key不存在时，添加value，key存在时，保留原来value
~~~~~~

字典的公共功能

~~~~~~~~
1.长度:len()
2.索引:字典[key] 或 字典.get() 后续多用后者
3.for循环
 1>获取所有键
   for 变量 in 字典:
   for 变量 in 字典.keys():
 2>获取所有值
   for 变量 in 字典.values():
 3>获取所有键值对
   for 变量1,变量2 in 字典.items():
~~~~~~~~

### 集合set()  (返回值集合)

作用

~~~~
1.储存非重复数据
2.去重
3.逻辑判断，交并差集
~~~~

集合数学运算

| 运算符操作 | python运算符 | 含义                                 |
| ---------- | ------------ | ------------------------------------ |
| 交集       | &            | 取两集合公共的元素                   |
| 并集       | \|           | 取两集合全部的元素                   |
| 差集       | -            | 取一个集合中另一集合没有的元素       |
| 成员运算   | in 和 not in | 判断一个某个元素是否在或者不在集合中 |

增

~~~~
add()
语法:集合名.add(元素)
~~~~

减

~~~
1.pop()
  语法:集合.pop()
  在集合元素是字符串，且在cmd运行中，会随机删除。在pycharm默认删除第一个
2.remove()
  语法:集合.remove(元素)
  元素不存在时会报错
3.discard()
  语法:集合.discard(元素)
  元素不存在时不会报错
4.clear()
  集合.clear()
  清空集合
5.del
  语法:del 集合
  删除集合
~~~

公共功能

~~~~~
1.len()
2.for循环
3.减(计算差集)
~~~~~

### 函数

#### 函数定义

语法

~~~~~~~~~
def 函数名(形参1,形参2....形参n):
    代码块
~~~~~~~~~

#### 函数调用

语法

~~~~~~~~
函数对象()
~~~~~~~~

#### 函数的参数

##### 形参

~~~~~~
定义函数时，def 函数名(形参)
~~~~~~

##### 实参

~~~~
调用函数时，函数名(实参)
~~~~

#### 参数的传递方式

##### 默认值参数

~~~
def 函数名(形参1，形参2，形参3=value)
形参3就是默认值参数
~~~

##### 位置参数和关键字参数

位置参数

~~~~~~
实参和形参一一对应
~~~~~~

关键字参数

~~~~~~~
利用参数名来传递
调用函数，函数名(实参1，实参2，形参4=value1，形参3=value2)
~~~~~~~

注意

~~~
1.两者可以混搭，但位置参数必须在关键字参数之前
2.实参可以传递任何类型的值
~~~

#### 函数的可变参数

解包和装包共同注意点

~~~~~~~~
星号多的写在星号少的后面
~~~~~~~~

##### 装包

内涵

~~~~~~~~
在调用函数时，把里面多余的实参进行封装成元组或字典
~~~~~~~~

*args

~~~~~
*args可以接受无穷多的参数
*args是把所有实参保存到一个元组中
*args只能接受位置参数
~~~~~

**kwargs

~~~~~
**kwargs接受任意关键字参数，并将所有实参保存到一个字典中
输入 key=value 的格式
~~~~~

##### 解包

内涵

~~~~~~
就是在调用函数且输入的实参为序列时，把序列中的元素提取出来
~~~~~~

注意

~~~
序列中的元素个数必须和函数中的形参个数一致
~~~

#### 函数的返回值

目的

~~~~~~
1.体现函数的功能，输入实参，得到返回值
2.结束函数
~~~~~~

注意

~~~~
1.return只能返回单值，若有多个元素，则封装成元组
2.return可以返回任意值包括函数
3.若没有标明return后面的值，则默认None
4.return可以出现多次,一旦履行一个，则结束函数
~~~~

#### 作用域

定义

~~~~~~
变量生效的区域
~~~~~~

全局作用域

~~~~~~~~~
全局作用域就是在全局都有效
生命周期：程序执行时创建，在程序执行解释时销毁
~~~~~~~~~

局部作用域

~~~~~~~~~~~~
局部作用域就是在局部都有效
生命周期：在函数调用时创建，在调用结束时销毁
~~~~~~~~~~~~

注意

~~~~~~~~~~
使用变量时，会优先在当前作用域中寻找该变量，没有就继续往上一级作用域寻找
~~~~~~~~~~

关键字 global

~~~~~~
语法：global 变量
     变量 = value
可以用局部变量修改全局变量
~~~~~~

#### 命名空间

locals

~~~~~~~
用于获取当前作用域的命名空间，返回的是一个字典
~~~~~~~

~~~~~
语法:获取全部--locals
    获取key--locals.keys()
    获取value--locals.values()
~~~~~

#### 匿名函数和递归函数

##### 高阶用法

1.引用函数

~~~~~~~~~~
def a():
	代码块
b = a
b()
~~~~~~~~~~

2.函数为参

~~~
def a():
	代码块
def b(x):
	代码块
    x()
b(a)
~~~

3.函数作为返回值

~~~~
def a():
	代码块
def b(x):
	代码块
	return x
c = b(a)
c() #也就相当于a()
~~~~

4.函数作为容器

~~~~~~
def a():
	代码块
li = [元素1，元素2，a]
b = li[2]
b()  #相当于a()
~~~~~~

##### 匿名函数 (lambda)

~~~~~~~~
语法:lanmbda 参数列表:运算表达式
~~~~~~~~

注意

~~~~~~~
1.不会提升程序运行效率，只能简洁代码
2.lambda中不要有内循环，降低可读性
3.lambda是为了减少函数定义，若一个函数只有一个返回值，只有一句代码，则使用   lambda
~~~~~~~

##### 内置函数

| 函数             | 语法                                 | 作用                                                         |
| ---------------- | ------------------------------------ | ------------------------------------------------------------ |
| abs()            | abs(参数)                            | 求绝对值                                                     |
| sum()            | sum(序列)                            | 求和                                                         |
| round()          | round(参数)                          | 四舍五入                                                     |
| map(func,seq)    | map(函数，序列)                      | 迭代器，对于序列中的元素分别执行函数(要看结果需要用list()或set()或tuple()转换) |
| filter(func,seq) | filter(函数，序列)                   | 过滤不符条件的元素,结果也要像map()一样转化                   |
| sorted()         | sorted(可迭代对象,key=,reverse=True) | 给序列排序(对比的是数字，字符串需要转型)                     |

- sum，求和
- divmod，求商和余数
- round，小数点后n位（四舍五入）
- min，最小值
- max，最大值
- all，是否全部为True
- any，是否存在True
- bin，十进制转二进制
- oct，十进制转八进制
- hex，十进制转十六进制
- ord，获取字符对应的unicode码点（十进制）
- chr，根据码点（十进制）获取对应字符
- enumerate, 可以将索引与元素组合为一个元组。
- len，长度
- print，打印
- input，输入
- type，查看类型
- range，可创建一个整数列表，一般用在 for 循环中
- id，查看内存地址

### 闭包与装饰器

#### 闭包定义

~~~~~~~~~
内部函数引用外部变量
~~~~~~~~~

#### 装饰器

~~~~~~~~~~~
目的:为函数添加新的功能
~~~~~~~~~~~

##### 基本模板

~~~~
def a():
	代码块
def b(x):
	def c():
		代码块
		x()
		代码块
	return c
a = b(a)
a()
~~~~

简洁方式

~~~~~~~~
def b(x):
	def c():
		代码块
		x()
		代码块
	return c
@ b    #相当于a = b(a)
def a():
	代码块
a()
~~~~~~~~

注意

~~~~
a()的形参应与c()和x()中的形参相同
~~~~

#### 总结

闭包

~~~~~~
闭包条件1.函数嵌套
	   2.内部函数运用外面参数
	   3.外部函数返回内部函数
~~~~~~

装饰器

~~~~
1.装饰器从本质上来看是一个闭包函数，同时也是函数嵌套
2.装饰器从效果上看是把a()转化成c()
~~~~

### 生成器与迭代器

列表生成式

~~~~~·
L = [x for x in range(11)]
printf(L)  #这个列表是占用内存的
~~~~~

#### 生成器

需要一个可迭代对象

~~~~~~
__next__ 不建议使用
next() 使用这个
~~~~~~

~~~~~~~~
创建生成器：
1.(x for x in range(1,11))
2.yield关键字实现
  def f():
  	print("hello world")
  	yield 1
  g = f()
  print(next(g))
~~~~~~~~

~~~~~~~~
g = (x for x in range(1,11))  #由于g不占用内存，需要用next()调用，然后生成
print(next(g))
print(next(g))
print(next(g))
print(next(g))
print(next(g))
print(next(g))
可以用for循环调用
for循环的本质是调用next()
所以可以用下面的代码替换

L = (x for x in range(1,6))
for i in L:
print(i)
~~~~~~~~

注:1. 垃圾回收机制:没有被对象引用时，python就会回收

~~~~~
a = 5
a = 10  由于a变成了10，若没有其他变量为5，那么5就会被回收
~~~~~

~~~:
yield 相当于具有存档意义的return
def a():
	print("f1")
	yield 1
	print("f2")
	yield 2
1.                                    2.
g = a()						   			for i in a():
print(next(g))								print(i)
print(next(g))

结果     f1
		1
		f2
		2
~~~

什么是可迭代对象？

~~~~
1.现象看，只要是可以for循环的都是可迭代对象
2.从本质上看，是内置有iter方法的是可迭代对象
~~~~

#### 迭代器

生成器就是迭代器

~~~~~~
l = [2,4,6]
d = iter(l) 
print(d) #<list_iterator object at 0x000001618FE786D8>
iterator是迭代器的意思
iterable可迭代对象
~~~~~~

~~~~~~
什么是迭代器
1.有iter()方法
2.有next方法
~~~~~~

~~~~~~~
for循环的内部本质就是3个事情：
1.调用可迭代对象的iter方法返回一个迭代器
2.不断地调用迭代器的next方法
3.处理异常
~~~~~~~

~~~~~~~
ator = (1,2,3)
print(ator)
while True:
    try:
        print(next(ator))
    except StopIteration:
        break
~~~~~~~

迭代器的优点

~~~~~~
1.为序列和非序列类型提供了一种统一的迭代取值方式
2.在需要时，用next()调用，那么就可以储存无限大的数据流
~~~~~~

#### 递归函数

1.自己调用自己

2.有终止条件

~~~~~~
其形成的样貌类似树，递归展开的时候，逐级下降，递归n个函数，那么就会有n个函数同时存在，所以递归函数容易超内存
~~~~~~

### 模块

#### 模块导入

~~~~~~~~
第一种：import模块名
将某个模块的整体导入到当前模块中
第二种：from 模块名 import 成员
将指定的成员导入到当前的模块中
第三种：from 模块名 import *
将指定模块的所有成员导入到当前模块中

导入成员，要防止名字相同，如果相同，就近原则

也可以 模块名 as 别名
~~~~~~~~

#### 隐藏成员

~~~~
被封装过了
模块中以_开头的文件，不会导入
但可以通过其他形式调用
~~~~

#### 模块变量

~~~~~
__file__:模块对应的文件路径
__name__:模块自身的名字
~~~~~

模块名字

~~~~~
1.在哪个模块开始运行，则那个模块__name__绑定__main__，且为主模块
2.非主模块名字就是真名
~~~~~

main标准语法

~~~~~~
if __name__ = '__main__':
	print("我是主程序")
~~~~~~

#### 模块分类

~~~~~~~~
1.内置模块，在内部就可以直接使用
print input
2.标准库模块，安装python的时候已经安装且可以直接使用
time、random
用的时候直接import导入就可以了
3.第三方模块，通常是开源的，需要自己安装
安装方法：
通过pip install模块名
卸载pip方法：pip unistall模块名
查询所有安装的第三方模块：pip list
PIP国内源：
1）清化大学
PIP源地址：https://pypi.tuna.tsinghua.edu.cn/simple
2）阿里云
PIP源地址：http://mirrors.aliyun.com/pypi/simple/
3）豆瓣
PIP源地址：http://pypi.douban.com/simple/
4）中国科学技术大学
PIP源地址：http://pypi.mirrors.ustc.edu.cn/simple/
5）华中科技大学
PIP源地址：http://pypi.hustunique.com/

pip install requests -i http://mirrors.aliyun.com/pypi/simple
~~~~~~~~

自己也可以写模块，让别人导入

### 包package

~~~~~~~~~~~
构成:语句-->函数-->类-->模块-->包
内涵:将模块以文件夹的形式分组管理--管理模块
~~~~~~~~~~~

#### 包的导入

~~~~~
和模块导入方式相同
~~~~~

#### 包的必要文件

~~~~~~
__init__.py
是包内必须存放的文件，在包加载的时候被自动调用
~~~~~~





~~~~~~~~
包的作用
1.对模块的统一管理
2.可以在__init__.py中写这个模块的使用说明
~~~~~~~~

#### 常用模块

~~~~
python的标准库:https://docs.python.org/3/py-modindex.html
~~~~

##### sys

~~~~~~~~~
用于与编译器交互
~~~~~~~~~

对应函数

~~~~~~
sys.modules 用于获取当前程序中引入的模块
	其返回值是字典，可以导入pprint模块，格式化输出
sys.path 获取模块的搜索路径
	返回一个列表
sys.exit() 退出程序
	括号内可以放数据，会打印出来(红色字体)
~~~~~~

##### os

~~~~~~~
用于和操作系统交互
~~~~~~~

对应函数

~~~~~~
os.system 用来写cmd指令
os.getcwd() 获取当前工作目录
os.lisdir(path) 列举path下的所有文件和目录
os.remove(path) 删除指定文件
os.rmdir(path) 删除指定目录
os.mkdir(path）建立指定目录
os.rename(path1,path2) 左边原名，右边新名
os.path.exists(path) 判断对象是否存在
os.path.isfile(path) 判断是否文件
os.path.isdir(path) 判断是否目录
~~~~~~

##### time

~~~~~~
time.time() 时间戳
time.localtime() 返回一个当地的时间元组
time.sleep(数字) 单位为秒
print(time.strftime('%Y-%m-%d %H:%M:%S'，time.localtime())) 
            格式化输出时间
~~~~~~

##### random

`````````
random.random() 生成一个0-1的随机数，左闭右开
random.randint(start,end) 整数，左闭右开
random.uniform(start,end) 小数，左闭右开
random.choice(['剪刀','石头'，‘布]，k=n) 随机返回n个值
`````````

##### json

~~~~~~~~~
文件储存形式
跨语言，跨平台
序列化和反序列化
~~~~~~~~~

``````
#序列化
json_data = json.dumps([1,2,'小川'])
print(type(json_data))
#序列化之后存储的是<class'str'>
#反序列化
data = json.loads(json_data)
print(data)
print(type(data))
#反序列化解码后是<class'list'>

将数据打包成json文件
with open(f'{存放路径}/{存放后名称}.json','w',encoding='utf-8')as f
 json.dump(要存放的数据,f)
 
 从json文件中提取数据
 with open(a,'r',encoding='utf-8')as f
        b = json.load(f)
``````

##### 正则表达式

~~~~~
import re
s1 = "abcdab"
pattern = "ab"
print(re.findall(pattern,s1))  #['ab','ab']
res = re.match(pattern,s1)
print(res)  #<_sre.SRE_Match object; span=(0, 2), match='ab'>
print(res.group())  #ab

match匹配到了，就返回结果，若匹配不上，则返回None
若匹配不上，则res.group()会报错
~~~~~

###### 元字符

~~~~~~
1. . 表示匹配单个字符，但除了\n
2.\d 表示0-9任意一个字符
3.\D 表示非数字
4.\s 表示空白字符\n \t 空格
5.\S 表示非空白
6.\w 表示英文字母，数字，下划线
7.\W 与\w相反
8.字符集 
	例子:print(re.match('[abcd]','abc')) #a
	使用中括号表示，表示字符范围
	例子:print(re.findall('[a-d]','zabc')) #['a','b','c']
	[a-d]等价于[abcd]
	
	注意 不能是[a-Z],需要[a-zA-Z]
9.^取反 [^a-e] 表示取 a-e 之外
10.字符串的多字符匹配
	print(re.match('[0-9][0-9]','1a')) #None
	print(re.match('[0-9][a-z]','1a')) #1a
~~~~~~

###### 数量规则

~~~~~
1.* 会匹配任意次数，包括0
2.+ 会匹配一次及以上次数
3.？ 会匹配0次或1次
4.{m} 匹配m次
5.{m,}匹配m次及以上
6.{m,n}匹配m次及以上，n次以下
~~~~~

###### 边界处理

~~~~~~~~
^表示开始，和字符集里面的取反区分
￥表示结束
用来限制匹配  ^表示开始就要匹配，否则返回None(match)或[](findall)
~~~~~~~~

###### 分组匹配

~~~~~~
|或者
()分组作用
t = '2022-12-01'
print(re.match('\d{4}-(0[1-9]|1[0-2])-([0-2]\d|[3][0-1])', t))  # <_sre.SRE_Match object; span=(0, 10), match='2022-12-01'>

group
t = '2022-12-01'
print(re.match('\d{4}-(0[1-9]|1[0-2])-([0-2]\d|[3][0-1])', t).group(0))  # 显示全部 2022-12-01
print(re.match('\d{4}-(0[1-9]|1[0-2])-([0-2]\d|[3][0-1])', t).group(1))  #  显示月份 12
print(re.match('\d{4}-(0[1-9]|1[0-2])-([0-2]\d|[3][0-1])', t).group(2))  # 显示天数  01
print(re.match('(\d{4})-(0[1-9]|1[0-2])-([0-2]\d|[3][0-1])', t).group(1))  # 显示年份 2022
print(re.match('(\d{4})-(0[1-9]|1[0-2])-([0-2]\d|[3][0-1])', t).group(3))  # 显示天数 01

print(re.match('(\d{4})-(0[1-9]|1[0-2])-([0-2]\d|[3][0-1])', t).groups())  # 把分组放到元组里面  ('2022', '12', '01')

由于匹配分组，最后生成的也成了元组

r 规避/  当
\1 代表第一个分组中的内容
\2 代表第二个分组中的内容
context = '<title>hello</title>'
print(re.match(r'<title>([\w\W]*)</title>',context))  # <_sre.SRE_Match object; span=(0, 20), match='<title>hello</title>'>
print(re.match(r'<(\w+)>([\w\W]*)</\1>',context).group(1))  # title

分组取别名  ?P<别名>
print(re.match(r'<(?P<tag>\w+)>([\w\W]*)</(?P=tag)>',context).group())  # <title>hello</title>
~~~~~~

### 文件操作

~~~~~~~
文件 --> file

步骤
1.打开文件

2.对文件进行操作，保存

3.关闭文件
~~~~~~~

#### 打开

~~~~
open(path, mode='r', buffering=-1, encoding=None, errors=None, newline=None, closefd=True, opener=None)

file = open(path)
print(file)
~~~~

~~~~~~~
路径(写路径时，加一个r，来规避反斜杠)
Ctrl+shift+c 复制绝对路径

相对路径
◆以“./”开头，代表当前目录和文件目录在同一个目录里，“./”也可以省略不写！

◆以"../"开头：向上走一级，代表目标文件在当前文件所在的上一级目录；

◆以"../../"开头：向上走两级，代表父级的父级目录，也就是上上级目录，再说明白点，就是上一级目录的上一级目录

◆以"/”开头，代表根目录
~~~~~~~

| 打开模式 |                          效果                          |
| :------: | :----------------------------------------------------: |
|    r     |               以读方式打开，文件必须存在               |
|    w     |    以写方式打开，文件不存在则创建，存在清空原有内容    |
|    a     | 以追加模式打开，文件不存在则创建，存在则继续进行写操作 |
|    r+    |              以读写模式打开 文件必须存在               |
|    w+    |   以读写模式打开文件，不存在则创建，存在清空原有内容   |
|    a+    | 追加并可读模式，文件不存在则创建，存在则继续进行写操作 |
|    rb    |                 以二进制读模式打开 同r                 |
|    wb    |                 以二进制写模式打开 同w                 |
|    ab    |                以二进制追加模式打开 同a                |
|   rb+    |               以二进制读写模式打开 同r+                |
|   wb+    |               以二进制读写模式打开 同w+                |
|   ab+    |               以二进制读写模式打开 同a+                |

#### 关闭

~~~~~
1.close()
2.with open...as
  	  代码块         #代码块执行完毕时，就会自动关闭
~~~~~

#### 读取

~~~~~~~~~~~
文件分类
1.纯文本文件(使用utf-8等编码编写的)
2.二进制文件(图片，音乐，视频)
~~~~~~~~~~~

read()

~~~~~~
括号里面带参数，则读取参数大小的数量，默认为-1，就是读取全部文件

with open(r"path",encoding="utf-8") as f:
    for i in range(4):
        content = f.read(4)
        print(content)        #如果读取完文件，会返回空字符串

读取大文件
all_content = ""
with open(r"path",encoding="utf-8") as f:
	while True:
		content = f.rand(4)
		if(content==' ')
			break
		all_content+=content
		
读取二进制文件的时候，其基本单位是字符不是字节
1kb = 1024byte  1mb = 1024kb
读取大小最好是1024的倍数
~~~~~~

readline()

~~~~~~~
一行一行读取    读完文件，会返回空字符串
with open(r"path",encoding="utf-8") as f:
    for i in range(4):
        content = f.readline()
        print(content)            
~~~~~~~

可以用f.write(字符串)写入

## 面向对象

### 面向过程和面向对象

~~~~~~~
面向过程:指的是解决问题的步骤，类似普遍性吧，从整体出发
面向对象:指的是了解事物的特性，也就是特殊性，从个体出发

二者相辅相成
~~~~~~~

定义类

~~~~
class 类名:
	可以写一些属性，被所有对象共享(用于描述一个类的共性)
	def __init__(self,...) 
		代码块
	def 方法名称(self,...)
		方法体               
类中所有变量为属性
类中所有函数为方法

Python中定义一个类使用class关键字
在给类起名字时，建议每个单词的首字母大写，其它字母小写
类其后要跟有冒号，提示python解释器，开始设计内部功能
__init__会自动运行，self必须要有，省略号放形参，若有形参，实例化时，必须传入
~~~~

创建对象(会同时开辟空间)

~~~~~~~
也是类的实例化
对象 = 类名()
对象.属性名 = 值
~~~~~~~

类调用

~~~~~
在我的理解里，用类调用就失去了面向对象本拥有的特殊性

实例成员大于类
1.实例方法
	定义:第一个参数必须是实例对象，该参数名一般约定为“self”，通过它来传递实例的属性和方法		  (也可以传类的属性和方法)
	调用:只能由实例对象调用
2.类方法
	定义:使用装饰器@classmethod，第一个参数必须是当前类对象，该参数名一般约定为“cls”，通		   过它来传递类的属性和方法(不能传实例的属性和方法)
	调用:实例对象和类对象都可以调用
3.静态方法
	定义:使用装饰器@staticmethod。参数随意，没有“self”和“cls”参数，但是方法体中不能使用		  类或实例的任何属性和方法  --> 相当于放在类里面的函数
	调用:实例对象和类对象都可以调用
	
当改变类变量的时候
~~~~~

### 三大特性

#### 封装

内涵

~~~~~
类中定义私有的属性和方法-->只有类的内部可以使用，外部(实例对象)无法访问
	用双下划线的方式隐藏属性和方法(设为私有)	
	
意义
	封装数据，控制外部对内部属性和方法操作
~~~~~

外部访问方法

~~~~~~~~
用 类名.__dict__  返回一个字典，里面私有属性和私有方法的名称

私有化就是把  __属性(方法)名 --> _类名__属性(方法)名

可以用新名字，但不要用这个访问方式，这样封装意义就没了
~~~~~~~~

将方法当作属性

~~~~
@property  用于其他属性改变来改变该属性的值
def 属性名(self):
	return self.__属性名
@属性名.setter  用于外界对于该属性赋值
def 属性名(self, value):
	self.__属性名= value
@属性名.deleter  用于删除属性名并改变其他变量的值
def 属性名(self)
	self.__属性名= value  删除属性名-->del 实例.属性名  (删除的是该实例的属性)

对象.属性名 = 数据
变量 = 对象.属性名


~~~~

#### 继承与多态

~~~~~~~
继承:能够拥有父类的功能
	class 类名(object):
	object是所有类的父类，默认为object
多态:父类的一种行为，在不同子类上有不同的实现
~~~~~~~

##### 继承

单继承和多继承

~~~~~
class father1():
	pass
class father2:
	pass

class son1(father1):  单继承
	pass

calss son2(father1,father2):  多继承
	pass
~~~~~

派生

~~~~
子类可以添加自己新的属性和方法
但当子类和父类拥有同样属性或方法时，就近原则
~~~~

继承的实现原理

~~~~~~~~
扩展
	c3线性算法实现的MRO构造

python对一个类，会计算一个方法解析顺序(MRO)列表，同时在MRO列表中，从左往右找查基类。知道找到第一个匹配的类为止

原则
1.子类先于父类
2.父类根据MRO中的顺序检查
3.对于下一个类存在两种合法选择(父类重名)，选择第一个父类

查找的方法
1.查找方式分两种，一种是深度优先和广度优先，python3只有广度优先，python2两个都有
2.python中类分为新式类(广度优先)和经典类(深度优先),所以python3只有新式类
	新式类就是继承了(object)的类，反之就是反式类
	
深度优先:会从子类一直走到底，找到最终的父类,都没有，再从子类换一个父类
广度优先:就是最底层的那个类(object)不先找,最后找，其他和深度一样
~~~~~~~~

组合

~~~~~
一个类的对象作为另一个类的数据
	举例:两个类，一个是士兵，一个是武器
				王二是士兵，剑是武器(实例化)
				剑可以作为王二的武器，就是作为数据输入
~~~~~

调用重名的函数

+ 指名道姓

  ~~~~~~~
  class Animal:
      def __init__(self, name, sex, age):
          self.name = name
          self.sex = sex
          self.age = age
          
      def eat(self):
          print("吃")
  
          
  class Dog(Animal):
      def __init__(self, name, sex, age, title): 
          Animal.__init__(name, sex, age)
          self.title = title
  ~~~~~~~

+ super()函数

  ~~~~~~
  class Animal:
      def __init__(self, name, sex, age):
          self.name = name
          self.sex = sex
          self.age = age
          
      def eat(self):
          print("吃")
  
          
  class Dog(Animal):
      def __init__(self, name, sex, age, title): 
          super().__init__(name, sex, age)
          self.title = title
          
  能够使用父类的方法
  super(type[, object-or-type])
  type -- 类。
  object-or-type -- 类，一般是 self
  ~~~~~~


##### 多态

~~~~~~~
定义:向不同对象发送同一个指令，不同对象在接受时，会产生不同的是行为(方法)

举例:指令:用刀
	对象:外壳医生(做手术)，厨师(做菜)，屠夫(砍肉)
~~~~~~~

一个接口，多实现

#### 内置函数

~~~~~~~
是所有类的父类(object)里面的
~~~~~~~

**base**和**bases**

~~~~~~
# __base__只查看从左到右继承的第一个子类
SubClass1.__base__
# __bases__则是查看所有继承的父类
SubClass2.__bases__
~~~~~~

**new**

~~~~~
class La(object):
    def __init__(self):
        print("__init__运行了")

    def __new__(cls, *args, **kwargs):
        print("可以用类名调用")
        return object.__new__(cls)

a = La()
#可以用类名调用
 __init__运行了
 
 1.__new__()无需使用 staticmethod 装饰器修饰
 2.__new__比__init__先运行
 3.__new__(cls)一定要返回一个实例对象，才会执行后面的__init__
~~~~~

**doc**

~~~~~~~~~~
class La(object):
    """知道吗，这里的雨季只有一两天"""
    def __init__(self):
    	pass
a = La()
print(a.__doc__)
#知道吗，这里的雨季只有一两天

用来输出类下面的注释内容
~~~~~~~~~~

**str**

~~~~
class La(object):
    def __init__(self):
        pass
    def __str__(self):
        return "相信"
a = La()
print(a)
#相信

打印实例名，会自动返回__str__中return的内容
~~~~

**call**

~~~~~~
class La(object):
    def __init__(self):
        pass
    def __call__(self, *args, **kwargs):
        print(f"".join(args))

a = La()
a("你在微笑吗")
#你在微笑吗

实例名+(),可以自动执行__call__方法
~~~~~~

**dict**    **module**    **class**

~~~~~~~
class La(object):
    def __init__(self, name):
        self.name = name

didi = La("alla")

dict
    print(didi.__dict__)
    print(La.__dict__)
    #{'name': 'alla'}
     {'__module__': '__main__', '__init__': <function La.__init__ at 		       0x000002892679AC80>, '__dict__': <attribute '__dict__' of 'La'               objects>, '__weakref__': <attribute '__weakref__' of 'La' objects>,           '__doc__': None}

     用于返回类和对象的所有成员

module
	print(didi.__module__)
	#__main__、
	
	用于返回哪个模块运行
	
class
	print(didi.__class__)
	#<class '__main__.La'>
	
	用于返回操作对象的类
~~~~~~~

**getitem**     **setitem**     **delitem**

~~~~~~
class La(object):
    def __init__(self):
        pass
    def __getitem__(self, item):
        print("__getitem__", item)
    def __setitem__(self, key, value):
        print(f"__setitem__,key是{key},value是{value}")
    def __delitem__(self, key):
        print("__delitem__", key)

dodo = La()
result = dodo["liu"]        自动执行__getitem__
dodo["jia"] = "you"		    自动执行__setitem__
del dodo["kun le"]		    自动执行__delitem__
#__getitem__ liu
 __setitem__,key是jia,value是you
 __delitem__ kun le
~~~~~~

**iter**

~~~~~
class Foo(object):
    def __init__(self, sq):
        self.sq = sq
    def __iter__(self):
        return iter(self.sq)

obj = Foo([11, 22, 33, 44])
for i in obj:
    print(i, end=" ")
#11 22 33 44 
    
迭代器，列表，字典和元组之所以能进行for循环，是因为内部定义了__iter__
~~~~~

**type**

~~~~~~~
python中一切事物都是对象，实例对象是对象，类也是对象
类也应该是通过执行某个类的构造方法创建
class Foo(object):
    def __init__(self):
        pass
dodo = Foo()
print(type(Foo), type(dodo))
#<class 'type'> <class '__main__.Foo'>

type类的构造类
def func(self):
    print('hello world')

Foo = type('Foo', (object,), {'func': func})
dodo = Foo()
dodo.func()
#hello world

# type第一个参数：类名
# type第二个参数：当前类的基类
# type第三个参数：类的成员

类里面有__metaclass__设置了一个type类的派生类，从而查看类的创建过程
~~~~~~~

描述符

内涵

~~~~~
描述符本质就是一个新式类,在这个新式类中,至少实现了`__get__(),__set__(),__delete__()`中的一个,这也被称为描述符协议
~~~~~

- __get__()`:调用一个属性时,触发 

  ~~~~~~~
  __getattr__和__getattribute__
  	class Foo(object):
      def __init__(self,jiayou):
          self.jiayou = jiayou
      def __getattribute__(self, item):
          print("__getattribute__")
          return "加油"
      def __getattr__(self, item):
          print("__getatter__")
  
      dodo = Foo("jiaoyou")
      print(dodo.jiayou)
      print(dodo.lala)
      #__getattribute__
      加油
      __getattribute__
      加油	
      
      有了__getattribute__就不会访问__dict__中的数据(属性)，访问属性的时候就会执行	       __getattribute__,而当访问不存在的数据的时候就会执行__getattr__
      访问优先级:__getattribute__ > __getattr__ > __dict__
  get
  	一个类只要实现了__get__，__set__，__delete__中任意一个方法，我们就可以叫它描述	     器,如果只定义了__get__我们叫非资料描述器，如果__set__，__delete__任意一个/或者     同时出现，我们叫资料描述器
  	
  	首先明确一点，拥有这个方法的类，应该(也可以说是必须)产生一个实例，并且这个实例是另外     一个类的类属性(注意一定是类属性，通过self的方式产生就不属于__get__范畴了
  	class Foo(object):
      def __get__(self, instance, owner):
          print("__get__")
          
      class Wwj(object):
          dodo = Foo()
  		def __init__(self):
          	self.dida = Foo()
      
      dola = Wwj()
      result = dola.dodo
      result1 = Wwj.dodo
      #__get__
       __get__
      如果用self.dida
      print(dola.dida)
      #<__main__.Foo object at 0x000001EBA51BC1D0>  也就成了普通的实例
  ~~~~~~~

- `__set__()`:为一个属性赋值时,触发

  ~~~~~~~
  若中间对上面的dodo重新赋值那么就脱离了描述其的关系，这时我们需要用__set__来永久绑定
  
  class Foo(object):
      def __get__(self, instance, owner):
          return "__get__"
      def __set__(self, instance, value):
          print("__set__")
          return "__set__"
  class Wwj(object):
      dodo = Foo()
  
  dola = Wwj()
  print(dola.dodo)
  dola.dodo = 1
  print(dola.dodo)
  print(dola.dodo)
  #__get__
   __set__
   __get__
   __get__
   
   由此观之，激活的时候执行__set__，但返回值一直都是__get__
  ~~~~~~~

- `__delete__()`:采用del删除属性时,触发

  ~~~~~~~~~
  class Foo(object):
      def __get__(self, instance, owner):
          return "__get__"
      def __delete__(self, instance):
          print("delete")
          return 1
  class Wwj(object):
      dodo = Foo()
dola = Wwj()
  print(dola.dodo)
  del dola.dodo
  #__get__
   delete
   
  道理相同，浅显易懂
  ~~~~~~~~~
  

## 异常处理和反射

### 异常处理

#### SyntaxError

~~~~~~~
语法错误，应在程序运行前改正
~~~~~~~

#### 运行时错误

|    异常类型    |                   含义                   |
| :------------: | :--------------------------------------: |
| AttributeError |  当试图访问的对象属性不存在时抛出的异常  |
|   IndexError   |       索引超出序列范围会引发此异常       |
|    KeyError    | 字典中查找一个不存在的关键字时引发此异常 |
|   NameError    |  尝试访问一个未声明的变量时，引发此异常  |
|   TypeError    |        不同类型数据之间的无效操作        |

#### 异常处理

~~~~~~~~~
try:
    被检测的代码块
except 异常类型：
    检测到异常，就执行这个位置的逻辑
~~~~~~~~~

~~~~~~~
try:
    被检测的代码块
except NameError:
    触发NameError时对应的处理逻辑
except IndexError:
    触发IndexError时对应的处理逻辑
except KeyError as alias:
    触发KeyError时对应的处理逻辑
~~~~~~~

**else**   **finally** 

在多分支except之后还可以跟一个else,（else必须跟在except之后，不能单独存在），只有在被检测的代码块没有触发任何异常的情况下才会执行else的子代码块



try还可以与finally连用可以使用try-except-finally的形式，也可以直接使用try-finally的形式，无论被检测的代码块是否触发异常，都会执行finally的子代码块，因此通常在finally的子代码块做一些回收资源的操作，比如关闭打开的文件

~~~~
try: 
    被检测的代码块 
except 异常类型1: 
    pass 
except 异常类型2: 
    pass 
...... 
else: 
    没有异常发生时执行的代码块 
finally: 
    无论有无异常发生都会执行的代码块
~~~~

**raise**

带参数

~~~~~~~~
a = 1
try:
    if a==1:
        raise ValueError("a==1")
except ValueError as e:
    print("引发异常", repr(e))
#引发异常 ValueError('a==1',)
~~~~~~~~

不带参数(默认异常是RuntimeError)

~~~~~~~~
a = 1
try:
    if a==1:
        raise
except RuntimeError as e:
    print("引发异常", repr(e))
#引发异常 RuntimeError('No active exception to reraise',)
~~~~~~~~

#### 断言

Python assert 语句，又称断言语句，可以看做是功能缩小版的 if 语句，它用于判断某个表达式的值，如果值为真，则程序可以继续往下执行；反之，Python 解释器会报 AssertionError 错误

~~~~~~
a = 25
assert 26<= a <=100
print("运行了")
#Traceback (most recent call last):
  File "C:/Users/86151/PycharmProjects/pythonProject/dad.py", line 2, in  <module>
    assert 26<= a <=100
AssertionError
~~~~~~

提高了程序的健壮性，经常作为程序初期测试和调试过程中的辅助工具

### 反射

更加灵活地操作成员，也是全新的访问方式

**内置函数**

- **getattr**     用于获取成员

  ~~~~~
  v1 = getattr(对象,"成员名称")
  v2 = getattr(对象,"成员名称", 不存在时的默认值)
  ~~~~~

- **setattr**     用于设置成员

  ~~~~~~
  setattr(对象,"成员名称",值)
  ~~~~~~

- **hasattr**    检测是否包含成员

  ~~~~~~~~
   = hasattr(对象,"成员名称") # True/False
  ~~~~~~~~

- delattr   删除成员

  ~~~~~~~~
  delattr(对象,"成员名称")
  ~~~~~~~~

例子

~~~~~~~~
class Account(object):
    def login(self):
        pass
    def register(self):
        pass
    def index(self):
        pass

def run():
    name = input("请输入要执行的方法名称：")
    account_object = Account()
    method = getattr(account_object, name, None)

    if not method:
        print("输入错误")
        return
    method()
~~~~~~~~

## MySQL

### 介绍

**用处**

~~~~~~
1.更好对数据分类保存
2.保护数据   
3.降低冗余
4.进行智能化分析
~~~~~~

**MySQL优势是什么**

~~~~~
1.开放的源代码的数据库
	任何人都可以获取该数据库的源代码，任何人都可以修正 MySQL 的缺陷
2.MySQL的跨平台性
3.功能强大且使用方便
~~~~~

**基本**

~~~~~~
行：记录    record
列：字段	field
~~~~~~

### 表操作

#### 创建表

~~~~~
create table 表名(
字段名1 类型[(宽度) 字段约束],
字段名2 类型[(宽度) 字段约束],
字段名3 类型[(宽度) 字段约束]
);

注意
	1. 在同一张表中，字段名是不能相同
	2. 宽度和约束可选
	3. 字段名和类型是必须的
~~~~~

**数据类型**

数字类型

~~~~~~~~~~
整数类型：INT，SMALLINT，TINYINT，MEDIUMINT，BIGINT
浮点类型：FLOAT，DOUBLE，DECIMAL
比特值类型：BIT
~~~~~~~~~~

![整型](/image/整型.png)

字符串类型

~~~~~
普通字符串： CHAR，VARCHAR
存储文本： text
存储二进制数据： BLOB
存储选项型数据：ENUM，SET

char：定长，即指定存储字节数后，无论实际存储了多少字节数据，最终都占指定的字节大小。默认只能存1字节数据。存取效率高。

varchar：不定长，效率偏低 ，但是节省空间，实际占用空间根据实际存储数据大小而定。必须要指定存储大小 varchar(50)

enum用来存储给出的多个值中的一个值,即单选，enum('A','B','C')

set用来存储给出的多个值中一个或多个值，即多选，set('A','B','C')
~~~~~

![字符串](/image/字符串.PNG)

字段约束**

非空约束（NOT NULL)

~~~~~~
哪个字段设置了非空约束，那个字段，在任何记录中都不能为空，其他字段可以空
~~~~~~

默认值（DEFAULT)

~~~~~~
如果插入的时候，没有给该字段赋值，那么系统就会给这个字段插入默认值
~~~~~~

唯一约束（UNIQUE KEY)

~~~~~
那个字段设置了唯一约束，那么这个字段就不能有重复的值，可以为空
可以有多个唯一约束
~~~~~

主键（PRIMARY KEY)

~~~~~
1.字段值唯一，这一点和唯一约束相同
2.字段值不能为空  与唯一约束不同
3.可以作为其他表的外键
4.一张表只能有一个主键
~~~~~

auto_increment

~~~~~
约束字段为自动增长，被约束的字段必须同时被key约束。一般用于主键
~~~~~

#### 修改表

~~~~~~
# 语法：alter table 表名 执行动作;

# 添加字段(add)
    alter table 表名 add 字段名 数据类型;
    alter table 表名 add 字段名 数据类型 first;
    alter table 表名 add 字段名 数据类型 after 字段名;
# 删除字段(drop)
    alter table 表名 drop 字段名;
# 修改数据类型(modify)
    alter table 表名 modify 字段名 新数据类型;
# 修改字段名(change)
    alter table 表名 change 旧字段名 新字段名 新数据类型;
# 表重命名(rename)
    alter table 表名 rename 新表名;
~~~~~~

#### 查看表结构命令

**DESCRIBE** 和 **SHOW CREATE TABLE** 命令来查看数据表的结构

- **DESCRIBE** 

  ~~~~~
  DESCRIBE/DESC 语句会以表格的形式来展示表的字段信息，包括字段名、字段数据类型、是否为主键、是否有默认值等，语法格式如下：
  
  DESCRIBE 表名;  
  或者简写成  
  DESC 表名;
  
  信息内涵
  	Null：表示该列是否可以存储 NULL 值
  	Key：表示该列是否已编制索引。PRI 表示该列是表主键的一部分，UNI 表示该列是 UNIQUE 索	        引的一部分
  	Default：表示该列是否有默认值，如果有，值是多少
  	Extra：表示可以获取的与给定列有关的附加信息，如 AUTO_INCREMENT 等
  ~~~~~

- **SHOW CREATE TABLE**

  ~~~~
  SHOW CREATE TABLE 命令会以 SQL 语句的形式来展示表信息。和 DESCRIBE 相比，SHOW CREATE TABLE 展示的内容更加丰富，它可以查看表的存储引擎和字符编码；另外，你还可以通过`\g`或者`\G`参数来控制展示格式
  
  SHOW CREATE TABLE 表名;
  ~~~~

#### 删除表

注:删除表记得备份，以免造成无法挽回的损失

**DROP TABLE** ：删除一个或多个数据表

~~~~~~
DROP TABLE [IF EXISTS] 表名1 [ ,表名2, 表名3 ...];

IF EXISTS 用于在删除数据表之前判断该表是否存在。如果不加 IF EXISTS，当数据表不存在时 MySQL 将提示错误，中断 SQL 语句的执行；加上 IF EXISTS 后，当数据表不存在时 SQL 语句可以顺利执行，但是会发出警告（warning）
~~~~~~

### 库操作

#### 创建数据库

~~~~~
CREATE DATABASE [IF NOT EXISTS] 库名 [character set utf8];
~~~~~

数据库命名规则：

- 可以由字母、数字、下划线、＠、＃、＄
- 唯一性
- 不能使用关键字如 create select
- 不能单独使用数字

#### 查看数据库

~~~~~
SHOW DATABASES;
~~~~~

- information_schema：主要存储了系统中的一些数据库对象信息，比如用户表信息、列信息、权限信息、字符集信息和分区信息等。
- mysql：MySQL 的核心数据库，主要负责存储数据库用户、用户访问权限等 MySQL 自己需要使用的控制和管理信息。常用的比如在 mysql 数据库的 user 表中修改 root 用户密码。
- performance_schema：主要用于收集数据库服务器性能参数。
- sys：sys 数据库主要提供了一些视图，数据都来自于 performation_schema，主要是让开发者和使用者更方便地查看性能问题。

#### 修改数据库

~~~~~~~~~~
ALTER DATABASE 数据库名 CHARSET 字符集名;
~~~~~~~~~~

#### 删除数据库

~~~~~~~~
DROP DATABASE [ IF EXISTS ] 数据库名
~~~~~~~~

使用 DROP DATABASE 命令时要非常谨慎，在执行该命令后，MySQL 不会给出任何提示确认信息。DROP DATABASE 删除数据库后，数据库中存储的所有数据表和数据也将一同被删除，而且不能恢复

#### 选择数据库

~~~~~~~
USE 数据库名
~~~~~~~

### 表数据基本操作

**INSERT    插入数据**

~~~~~~~
# 1. 插入完整数据（顺序插入）
# 语法一：
INSERT INTO 表名(字段1,字段2,字段3…字段n) VALUES(值1,值2,值3…值n);

# 语法二：
INSERT INTO 表名 VALUES (值1,值2,值3…值n);

# 2. 指定字段插入数据
INSERT INTO 表名(字段1,字段2,字段3…) VALUES (值1,值2,值3…);

# 3. 插入多条记录
INSERT INTO 表名 VALUES
(值1,值2,值3…值n),
(值1,值2,值3…值n),
(值1,值2,值3…值n);
~~~~~~~

**SELECT  数据表查询语句**

~~~~~~~
select * from 表名 [where 条件];
select 字段1,字段2 from 表名 [where 条件];
~~~~~~~

- where子句

  - 算术运算符

    ![算数](/image/算数.png)

  - 比较运算符

    ![比较](/image/比较.png)

  - 逻辑运算符

    ![逻辑](/image/逻辑.png)

**UPDATE    修改数据**

~~~~~~~~~~
update 表名 set 字段1=值1,字段2=值2,... where 条件;

# 注意:update语句后如果不加where条件,所有记录全部更新
~~~~~~~~~~

**DELETE  删除数据**

~~~~~~
delete from 表名 where 条件;

# 注意:delete语句后如果不加where条件,所有记录全部清空
~~~~~~

**时间类型数据**

- 日期 ： DATE
- 日期时间： DATETIME，TIMESTAMP
- 时间： TIME
- 年份 ：YEAR

![时间](/image/时间.PNG)

- 时间格式

  ~~~~~~
  date ："YYYY-MM-DD"
  time ："HH:MM:SS"
  datetime ："YYYY-MM-DD HH:MM:SS"
  timestamp ："YYYY-MM-DD HH:MM:SS"
  ~~~~~~

  - datetime ：以系统时间存储
  - timestamp ：以标准时间存储但是查看时转换为系统时区，所以表现形式和datetime相同

- 日期时间函数
  - now()  返回服务器当前日期时间,格式对应datetime类型
  - curdate() 返回当前日期，格式对应date类型
  - curtime() 返回当前时间，格式对应time类型

- 时间操作

  时间类型数据可以进行比较和排序等操作，在写时间字符串时尽量按照标准格式书写

### 查询语法进阶

**模糊查询**

~~~~~~
LIKE
SQL LIKE 子句中使用百分号` %`来表示任意0个或多个字符
	例如:a%b`表示以字母 a 开头，以字母 b 结尾的任意长度的字符串

下划线`_`表示任意一个字符
	例如:`a_b`可以代表 acb、adb、aub 等字符串
~~~~~~

**AS:设置别名**

~~~~~~~~
1.为表指定别名
2.为字段指定别名

区别:表别名只在执行查询时使用，并不在返回结果中显示
    字段定义别名之后，会返回给客户端显示，显示的字段为字段的别名
~~~~~~~~

**ORDER BY: 对查询结果排序**

~~~~~~
通过条件查询语句查询到的数据一般都是按照数据最初被添加到表中的顺序来显示
因此，MySQL 提供了 ORDER BY 关键字来对查询结果进行排序

语法:
SELECT field1, field2,...fieldN FROM table_name1 WHERE field1
ORDER BY field1 [ASC [DESC]]

介绍:
ORDER BY 子句来设定你想按哪个字段哪种方式来进行排序，再返回搜索结果
ASC|DESC：`ASC`表示字段按升序排序；`DESC`表示字段按降序排序

~~~~~~

**LIMIT  限制查询结果的条数**

~~~~~~
LIMIT 子句用于限制由 SELECT 语句返回的数据数量 或者 UPDATE,DELETE语句的操作数量

语法:
SELECT column1, column2, columnN 
FROM table_name
WHERE field
LIMIT [num]
~~~~~~

**子查询**

~~~
介绍
    子查询是 MySQL 中比较常用的查询方法，通过子查询可以实现多表查询
    子查询指将一个查询语句嵌套在另一个查询语句中
    子查询可以在 SELECT、UPDATE 和 DELETE 语句中使用，而且可以进行多层嵌套
    在实际开发时，子查询经常出现在 WHERE 子句中
    
 WHERE 子句基本语法
 	SELECT column_name [, column_name ]
	FROM   table1 [, table2 ]
	WHERE  column_name OPERATOR
    	   (SELECT column_name [, column_name ]
            FROM table1 [, table2 ]
            [WHERE])
  子句结果作为一个值使用时，返回的结果需要一个明确值，不能是多行或者多列
  如果子句结果作为一个集合使用，即where子句中是in操作，则结果可以是一个字段的多个记录

FROM 子句基本语法
    SELECT column_name [, column_name ]
    FROM (SELECT column_name [, column_name ]
          FROM table1 [, table2 ]
          [WHERE]) AS temp_table_name
     WHERE  condition
  需要将子查询结果集重命名一下，方便where子句中的引用操作
~~~



### python_lala

1. 函数不仅可以用来得到一个值，在搭配上if，还可以使一段代码自动重复使用
2. 当然用循环加if也可以重复使用(可以用不同条件下break来退出循环，可用函数最后return break)
6. 判断是否有该文件

~~~~~~
import json
import os
def check():
    a = f'{存放路径}/{存放后的名称}.json'
    if os.path.exists(a)
    with open(a,'r',encoding='utf-8')as f
        b = json.load(f)
        return b
~~~~~~

5. 打印列表，想要把里面的数据变得整洁可以用for循环，也可以用           pprint()

6. ~~~~
   __str__方法可以改变打印对象的信息
   ~~~~

