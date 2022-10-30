## git

#### git的淘宝镜像源

~~~~
https://registry.npmmirror.com/binary.html?path=git-for-windows/
~~~~

#### windows操作

~~~~~~~
使用git bash要用
    git config core.autocrlf false (仅对当前git仓库有效）
    git config --global core.autocrlf false (全局有效，不设置推荐全局）
使得windows也用LF换行
~~~~~~~

打开DOS命令窗口：win+r，输入cmd

##### 1、常用DOS命令

~~~~~~~~~
help——帮助
cls——清屏
Tab键——补全文件名
date——显示或设置日期
time——显示或设置系统时间
start——打开指定程序/网页/文件等
exit——关闭cmd运行程序
ctrl+c——中止命令执行
~~~~~~~~~

##### 1、文件操作相关命令

~~~~~
d:——进入d磁盘
cd——切换目录
cd..——返回上一级目录
md、mkdir——创建文件夹在当前目录下
echo、copy con——创建文本并编辑
 注：（ctrl+z 回车结束编写；echo只能单行输入编写、echo con可以多行输入编写文本）
ren——重新命名文件（ren 原名称  修改后名）
move——移动文件（move 移动文件名  移动到的位置）
dir——显示一个目录中的文件和子目录
type——显示文本文件内容
	type 文件名    （查看文件内容）
	type 文件名 |more （分页显示）
del、erase——删除至少一个文件
	del 文件名 （删除一个）
	del *.txt （删除目录下所用.txt文件）
	del *.* （删除所用）
rd、rmdir——删除目录
~~~~~

#### GIT的操作

##### 基础

**查看配置和初始化**

~~~~~~~~~
git init                                                  # 初始化本地git仓库
git config --global user.name "xxx"                       # 配置用户名
git config --global user.email "xxx@xxx.com"              # 配置邮件
git config -l                                             #展现所有配置
git config --global -- list                               #全局配置
git config -- system -- list                              #系统配置
git status                                                # 查看当前状态
~~~~~~~~~

###### 三大区间图

![关系图](/../关系图.jpg)

###### work和index

~~~~~
work --> index 
    git add xyz                                      # 添加xyz文件至index
    git add .                                        # 增加当前子目录下所有
index --> work
	git rm --cached file                             #从index到工作区
	git reset file							         #回滚至工作区的 文件未修改时状态
	git reset HEAD file                       	     #回滚至工作区的 文件修改之后状态
~~~~~

###### index和repository

~~~~~~
index --> repository
	git commit -m 'xxx'                              # 提交
	git commit --amend -m 'xxx'                      # 合并上一次提交（用于反复修改）

repository --> index
	版本回退
~~~~~~

###### 版本回退

**查看版本**

~~~~~~
git log           查看所有版本
git log -n        显示n-1行版本，n是数字
~~~~~~

**实现回退**

~~~~~~~
git reset 版本
git reset --hard 版本

git revert 版本
~~~~~~~

**回退版本回退**

~~~~~
git reflog                                查看操作，来查看之前的版本
~~~~~

**两者区别**

~~~~~
现在有两个版本 
版本1 -->  版本2       如今要从版本2到版本1

reset  
	版本1
revert 
	版本1 --> 版本2 --> 版本1
~~~~~

###### 删除文件

~~~~~~~~
git rm -f file                                       index中 强制删除
git rm file                                          库中

windows系统中del哪里的文件都可以删除
~~~~~~~~

###### 恢复文件

**删除的文件**

用git命令删除，想要恢复，必须已经提交到版本库，才能恢复

~~~~~~~~~~~
1.提交删除信息  git commit -m
2.回退版本   git reset --hard 版本号      -->实现将文件变为未跟踪状态
3.git restore file

或者
1.git restore --staged   将文件变为未跟踪状态
	也可以用git reset 将里面所有文件变为未跟踪状态
2.git restore file 
~~~~~~~~~~~

用del windows命令删除，只要不是在工作区中，都可以恢复

~~~~~~~
git restore file
~~~~~~~

**修改的文件**

~~~~~~
1.git restore file

2.git checkout file

3.提交修改信息，版本回退

在缓存区修改，则恢复到缓存区，仓库中修改，则恢复到仓库
~~~~~~

###### 别名

**设置别名**

```
git config --global alias.a add
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.co checkout
git config --global alias.st status
```

**取消别名**

~~~~~~~~
git config --global --unset alias.a
~~~~~~~~

##### 进阶

###### gitignore语法

**忽略文件**

~~~~~~~
# 忽略 .a 文件
*.a
# 但否定忽略 lib.a, 尽管已经在前面忽略了 .a 文件
!lib.a
# 仅在当前目录下忽略 TODO 文件， 但不包括子目录下的 subdir/TODO
/TODO
# 忽略 build/ 文件夹下的所有文件
build/
# 忽略 doc/notes.txt, 不包括 doc/server/arch.txt
doc/*.txt
# 忽略所有的 .pdf 文件 在 doc/ directory 下的
doc/*=*/*.pdfaqA
~~~~~~~

###### stash的操作

用处

~~~~~~~~~~
对于进行一半的工作且有其他分支要处理，可以利用stash将工作推入堆栈(堆栈主要指的是栈，堆需要程序员自己开辟内存)中，并在需要的时候提取出来
~~~~~~~~~~

1.保存所有未提交的文件

~~~~~
git stash
~~~~~

2.恢复之前的工作目录

~~~~
git stash pop  删除堆栈中的第一个stash，并将修改应用到当前工作目录下
git stash apply 可以将缓存堆栈中的stash多次应用到工作目录，且不删除stash拷贝
~~~~

3.查看现有的stash

~~~~
git stash list

一个典型输出
stash@{0}: WIP on master: 049d078 added the index file
stash@{1}: WIP on master: c264051 Revert "added file_size"
stash@{2}: WIP on master: 21d80a5 added number to log

git stash show 显示做了哪些改动

可以用git stash show stash@{1}显示第二个
也可以用git stash apply stash@{1} 来使用第二个
~~~~

4.移除stash

~~~~~~~~
git stash drop 后面可以跟stash名字
git stash clear 可以清除所有缓存的stash
~~~~~~~~

5.stash 建立分支

~~~~
git stash branch 分支名字
~~~~



##### 5培训

~~~~~~~
git log 查看提交
git reset --hard 版本 强制回退
git relog  查看操作
git remote add origin git @地址
git breanch -M master   远程仓库需要建立主分支
git push -u origin master  推送到远程仓库
git clone 地址 
~~~~~~~



