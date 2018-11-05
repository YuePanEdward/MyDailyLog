# Coming back to WHU

# Come on, fight for your dream.


# 9.28

## int main (int argc, char argv[]) 含义

argc：命令行总的参数的个数,即argv中元素的格式。

* argv[ ]: 字符串数组,用来存放指向你的字符串参数的指针数组,每一个元素指向一个参数

* argv[0]:指向程序的全路径名

* argv[1]:指向在DOS命令行中执行程序名后的第一个字符串。

* argv[2]:指向第二个字符串



# 10.7
## Do not go gently into that good dream.
## Rage,rage，against the dying of light.


# 10.8

Please work hard, for your final dream.

Don't be disturbed by those girls.


# 10.14

## How to use fortran90

gfortran -o hello helloworld.f90

./hello

gfortran -o  应用程序名 代码段名.f90

## How to use tensorflow

     import tensorflow as tf
     tf.enable_eager_execution()
 
     A = tf.constant([[1, 2], [3, 4]])
     B = tf.constant([[5, 6], [7, 8]])
     C = tf.matmul(A, B)

     print(C)

## Output: 

    tf.Tensor(
    [[19 22]
    [43 50]], shape=(2, 2), dtype=int32)
    
 # How to use VI 
 
 vi/vim 基本使用方法 
vi编辑器是所有Unix及Linux系统下标准的编辑器，它的强大不逊色于任何最新的文本编辑器，这里只是简单地介绍一下它的用法和一小部分指令。由于对Unix及Linux系统的任何版本，vi编辑器是完全相同的，因此您可以在其他任何介绍vi的地方进一步了解它。Vi也是Linux中最基本的文本编辑器，学会它后，您将在Linux的世界里畅行无阻。

1、vi的基本概念 
 基本上vi可以分为三种状态，分别是命令模式（command mode）、插入模式（Insert mode）和底行模式（last line mode），各模式的功能区分如下：

1) 命令行模式command mode）

控制屏幕光标的移动，字符、字或行的删除，移动复制某区段及进入Insert mode下，或者到 last line mode。

2) 插入模式（Insert mode）

只有在Insert mode下，才可以做文字输入，按「ESC」键可回到命令行模式。

3) 底行模式（last line mode）

将文件保存或退出vi，也可以设置编辑环境，如寻找字符串、列出行号……等。

不过一般我们在使用时把vi简化成两个模式，就是将底行模式（last line mode）也算入命令行模式command mode）。

2、vi的基本操作 
a) 进入vi

在系统提示符号输入vi及文件名称后，就进入vi全屏幕编辑画面：

$ vi myfile

不过有一点要特别注意，就是您进入vi之后，是处于「命令行模式（command mode）」，您要切换到「插入模式（Insert mode）」才能够输入文字。初次使用vi的人都会想先用上下左右键移动光标，结果电脑一直哔哔叫，把自己气个半死，所以进入vi后，先不要乱动，转换到「插入模式（Insert mode）」再说吧！

b) 切换至插入模式（Insert mode）编辑文件

在「命令行模式（command mode）」下按一下字母「i」就可以进入「插入模式（Insert mode）」，这时候你就可以开始输入文字了。

c) Insert 的切换

您目前处于「插入模式（Insert mode）」，您就只能一直输入文字，如果您发现输错了字！想用光标键往回移动，将该字删除，就要先按一下「ESC」键转到「命令行模式（command mode）」再删除文字。

d) 退出vi及保存文件

在「命令行模式（command mode）」下，按一下「：」冒号键进入「Last line mode」，例如：

: w filename （输入 「w filename」将文章以指定的文件名filename保存）

: wq (输入「wq」，存盘并退出vi)

: q! (输入q!， 不存盘强制退出vi)

3、命令行模式（command mode）功能键 
1）. 插入模式

按「i」切换进入插入模式「insert mode」，按“i”进入插入模式后是从光标当前位置开始输入文件；

按「a」进入插入模式后，是从目前光标所在位置的下一个位置开始输入文字；

按「o」进入插入模式后，是插入新的一行，从行首开始输入文字。

2）. 从插入模式切换为命令行模式

按「ESC」键。

3）. 移动光标

vi可以直接用键盘上的光标来上下左右移动，但正规的vi是用小写英文字母「h」、「j」、「k」、「l」，分别控制光标左、下、上、右移一格。

按「ctrl」+「b」：屏幕往“后”移动一页。

按「ctrl」+「f」：屏幕往“前”移动一页。

按「ctrl」+「u」：屏幕往“后”移动半页。

按「ctrl」+「d」：屏幕往“前”移动半页。

按数字「0」：移到文章的开头。

按「G」：移动到文章的最后。

按「$」：移动到光标所在行的“行尾”。

按「^」：移动到光标所在行的“行首”

按「w」：光标跳到下个字的开头

按「e」：光标跳到下个字的字尾

按「b」：光标回到上个字的开头

按「#l」：光标移到该行的第#个位置，如：5l,56l。

4）. 删除文字

「x」：每按一次，删除光标所在位置的“后面”一个字符。

「#x」：例如，「6x」表示删除光标所在位置的“后面”6个字符。

「X」：大写的X，每按一次，删除光标所在位置的“前面”一个字符。

「#X」：例如，「20X」表示删除光标所在位置的“前面”20个字符。

「dd」：删除光标所在行。

「#dd」：从光标所在行开始删除#行

5）. 复制

「yw」：将光标所在之处到字尾的字符复制到缓冲区中。

「#yw」：复制#个字到缓冲区

「yy」：复制光标所在行到缓冲区。

「#yy」：例如，「6yy」表示拷贝从光标所在的该行“往下数”6行文字。

「p」：将缓冲区内的字符贴到光标所在位置。注意：所有与“y”有关的复制命令都必须与“p”配合才能完成复制与粘贴功能。

6）. 替换

「r」：替换光标所在处的字符。

「R」：替换光标所到之处的字符，直到按下「ESC」键为止。

7）. 恢复/撤消/还原上一次操作

「u」：如果误执行一个命令，可以马上按下「u」，撤消上一个操作。按多次“u”可以执行多次撤消。

8）. 更改

「cw」：更改光标所在处的字到字尾处

「c#w」：例如，「c3w」表示更改3个字

9）. 跳至指定的行

「ctrl」+「g」列出光标所在行的行号。

「#G」：例如，「15G」，表示移动光标至文章的第15行行首。

4、Last line mode下命令简介 
 在使用「last line mode」之前，请记住先按「ESC」键确定您已经处于「command mode」下后，再按「：」冒号即可进入「last line mode」。

A) 列出行号

「set nu」：输入「set nu」后，会在文件中的每一行前面列出行号。

B) 跳到文件中的某一行

「#」：「#」号表示一个数字，在冒号后输入一个数字，再按回车键就会跳到该行了，如输入数字15，再回车，就会跳到文章的第15行。

C) 查找字符

「/关键字」：先按「/」键，再输入您想寻找的字符，如果第一次找的关键字不是您想要的，可以一直按「n」会往后寻找到您要的关键字为止。

「?关键字」：先按「?」键，再输入您想寻找的字符，如果第一次找的关键字不是您想要的，可以一直按「n」会往前寻找到您要的关键字为止。

D) 保存文件

「w」：在冒号输入字母「w」就可以将文件保存起来。

E) 离开vi

「q」：按「q」就是退出，如果无法离开vi，可以在「q」后跟一个「!」强制离开vi。

「qw」：一般建议离开时，搭配「w」一起使用，这样在退出的时候还可以保存文件。

5、vi命令列表 
1、下表列出命令模式下的一些键的功能：

h 
左移光标一个字符

l 
右移光标一个字符

k 
光标上移一行

j 
光标下移一行

^ 
光标移动至行首

0 
数字“0”，光标移至文章的开头

G 
光标移至文章的最后

$ 
光标移动至行尾

Ctrl+f 
向前翻屏

Ctrl+b 
向后翻屏

Ctrl+d 
向前翻半屏

Ctrl+u 
向后翻半屏

i 
在光标位置前插入字符

a 
在光标所在位置的后一个字符开始增加

o 
插入新的一行，从行首开始输入

ESC 
从输入状态退至命令状态

x 
删除光标后面的字符

#x 
删除光标后的＃个字符

X 
(大写X)，删除光标前面的字符

#X 
删除光标前面的#个字符

dd 
删除光标所在的行

#dd 
删除从光标所在行数的#行

yw 
复制光标所在位置的一个字

#yw 
复制光标所在位置的#个字

yy 
复制光标所在位置的一行

#yy 
复制从光标所在行数的#行

p 
粘贴

u 
取消操作

cw 
更改光标所在位置的一个字

#cw 
更改光标所在位置的#个字

下表列出行命令模式下的一些指令 
w filename 
储存正在编辑的文件为filename

wq filename 
储存正在编辑的文件为filename，并退出vi

q! 
放弃所有修改，退出vi

set nu 
显示行号

/或? 
查找，在/后输入要查找的内容

n 
与/或?一起使用，如果查找的内容不是想要找的关键字，按n或向后（与/联用）或向前（与?联用）继续查找，直到找到为止。

# 10.15 Learn something about ubuntu and tensorflow

## Ubuntu 命令
类似任务管理器 top
管理员权限 sudo
改密码 passwd

## 关于点云covariance and cross-covariance
 推荐太一吾鱼水的blog: https://www.cnblogs.com/yhlx125/p/5767519.html
 
## Write the Introduction and related work part of my paper
## Read the original ICP paper and try to understand the part of convergence domain
## MMT2019

# 10.17 
About NDT
太一吾鱼水的blog： https://www.cnblogs.com/yhlx125/p/5749770.html

# 10.18 
### 测试 LeGO-LOAM 算法
https://github.com/YuePanEdward/LeGO-LOAM
千万记得装完之后（catkin_make)之后要Source 一下~/catkin_ws/devel/setup.bash

否则会报找不到node源文件的错

可编译运行，但是找不到输入点云，要么是rosbag，要么是tf的错

找时间再看下吧

### 写 paper

# 10.19
### Ptr 定义的时候一定注意加（）
格式: XXXPtr objectname(new XXX());
Example:  pcXYZIPtr pointcloud1(new pcXYZI());

### 直方图相似度计算
https://www.cnblogs.com/xuqq/articles/3997072.html

# 10.20
### Don't be so stupid /foolish/idiot anymore
If(int i=0;i<30;i++){}
第一个初始条件  第二个执行条件  第三个执行结束操作
你他妈别再脑子晕的犯这种低级错误了

# 10.22
别再秀逗了
### Linux
写脚本的时候注意啊

#!/bin/bash

作为开头，记住了

### Fortran基本用法
http://blog.sina.com.cn/s/blog_6dba2a9e01011nmw.html

# 10.24
Today is the programmer's day.
## Hello World! 

# 10.25
Ultra-Edit 下载
### 任务
1.英语 口语，写作

2.fortran 看复习PPT

3.实验跑着，paper写着

4.申请加油，看下EPFL

### 感觉自己好菜啊。代码老是出Bug

# 10.26
人生的低谷，也要坚强地走过啊。
You must walk through all the highs and lows of your life to be a real man.

## IoU （Intersection over Union) 交并比的概念

https://blog.csdn.net/iamoldpan/article/details/78799857

以及IoU threshold 对于IoU的Non-Maximum Suppression非极大抑制

# 10.30 
将Windows下程序转移至Linux下

## CmakeLists.txt的写法
   
    project(GHICP)

    cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

    #--- Eigen3
    find_package(Eigen3 REQUIRED)
    include_directories(${EIGEN3_INCLUDE_DIRS})

    #--- PCL
    find_package(PCL 1.6 REQUIRED)
    include_directories(${PCL_INCLUDE_DIRS})
    link_directories(${PCL_LIBRARY_DIRS})
    add_definitions(${PCL_DEFINITIONS})

    add_executable(GHICP           
	  main.cpp
	  dataio.cpp
       fpfh.cpp
	  BinaryFeatureExtraction.cpp
	  KM.cpp
	  principleComponentAnalysis.cpp
       Registration.cpp
       StereoBinaryFeature.cpp
	  )

    target_link_libraries (GHICP ${PCL_LIBRARIES})

## 常见问题
PCL编译问题  
Bug1 VTK问题1 要装一个 libpcl.dev
Bug2 VTK问题2
      
      [ 50%] Building CXX object CMakeFiles/pcd_write.dir/pcd_write.cpp.o
     <command-line>:0:15: warning: missing whitespace after the macro name
     make[2]: *** No rule to make target '/usr/lib/x86_64-linux-gnu/libproj.so', needed by 'pcd_write'.  Stop.
     CMakeFiles/Makefile2:67: recipe for target 'CMakeFiles/pcd_write.dir/all' failed
     make[1]: *** [CMakeFiles/pcd_write.dir/all] Error 2
     Makefile:83: recipe for target 'all' failed
     make: *** [all] Error 2
     -- Found OpenNI2: /usr/lib/libOpenNI2.so  
     ** WARNING ** io features related to pcap will be disabled
     ** WARNING ** io features related to png will be disabled
     -- The imported target "vtkRenderingPythonTkWidgets" references the file
     "/usr/lib/x86_64-linux-gnu/libvtkRenderingPythonTkWidgets.so"
     but this file does not exist.  Possible reasons include:
     * The file was deleted, renamed, or moved to another location.
     * An install or uninstall procedure did not complete successfully.
     * The installation package was faulty and contained
     " /usr/lib/cmake/vtk-6.2/VTKTargets.cmake"
      but not all the files it references.
      
 解决方法
 
   第一步 
      
    sudo apt install libproj-dev
  
   第二步

    add the following line to your CMakeLists.txt file:
    list(REMOVE_ITEM PCL_LIBRARIES "vtkproj4")

迁移OS问题
    
   1.include的时候全得用往左的斜杠 / 而不是 \ 。
    
   记好了。否则Linux不认会报错
   
   2.还有<Eigen/Dense>也不认，还是改成<Eigen/Eigen>,虽然不知道为什么
   
   3.有时会有typename问题
   
     error: need 'typename' before 'std::vector<MarkPoint<T>>::const_iterator' because 'std::vector<MarkPoint<T>>::const_iterator is a depedent scope'
    
   解决方法，在前面直接加个typename,详见https://blog.csdn.net/Felaim/article/details/78641635 


## SuperVoxel 超体素

An example of supervoxels and adjacency graph generated for a cloud

Segmentation algorithms aim to group pixels in images into perceptually meaningful regions which conform to object boundaries. Graph-based approaches, such as Markov Random Field (MRF) and Conditional Random Field (CRF), have become popular, as they merge relational low-level context within the image with object level class knowledge. The cost of solving pixel-level graphs led to the development of mid-level inference schemes which do not use pixels directly, but rather use groupings of pixels, known as superpixels, as the base level for nodes. Superpixels are formed by over-segmenting the image into small regions based on local low-level features, reducing the number of nodes which must be considered for inference.

Due to their strong impact on the quality of the eventual segmentation, it is important that superpixels have certain characteristics. Of these, avoiding violating object boundaries is the most vital, as failing to do so will decrease the accuracy of classifiers used later - since they will be forced to consider pixels which belong to more than one class. Additionally, even if the classifier does manage a correct output, the final pixel level segmentation will necessarily contain errors. Another useful quality is regular distribution over the area being segmented, as this will produce a simpler graph for later steps.

Voxel Cloud Connectivity Segmentation (VCCS) is a recent “superpixel” method which generates volumetric over-segmentations of 3D point cloud data, known as supervoxels. Supervoxels adhere to object boundaries better than state-of-the-art 2D methods, while remaining efficient enough to use in online applications. VCCS uses a region growing variant of k-means clustering for generating its labeling of points directly within a voxel octree structure. Supervoxels have two important properties; they are evenly distributed across the 3D space, and they cannot cross boundaries unless the underlying voxels are spatial connected. The former is accomplished by seeding supervoxels directly in the cloud, rather than the projected plane, while the latter uses an octree structure which maintains adjacency information of leaves. Supervoxels maintain adjacency relations in voxelized 3D space; specifically, 26-adjacency- that is neighboring voxels are those that share a face, edge, or vertex, as seen below.

Over-segmentation 过分割
Under-segmentation 欠分割


   
