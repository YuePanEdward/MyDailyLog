# 1.3
Please Work hard.

# 1.4
一堆让人崩溃的问题

1.Vector的定义冲突 using namespace std 还是少用，宁可多写点std::

一个傻逼错误，在别处定义了Vector,则std下的Vector被覆盖了。

2.STL检查对于PCL版本不兼容问题，还有预编译器的问题

https://blog.csdn.net/qing101hua/article/details/70739391

3.stdafx.h 的问题 

https://blog.csdn.net/u013057085/article/details/50741114

4.PCL ply格式读取

https://www.cnblogs.com/BambooEatPanda/p/7551825.html

5.全局宏定义max,min与PCL模板定义max,min冲突，解决方案

https://blog.csdn.net/zhuangshn/article/details/5537499

# 1.5
一个傻逼错误啊

http://blog.chinaunix.net/uid-26808060-id-3345409.html

记住 头文件开头的
     
     #ifndef PCA_H
     #define PCA_H
     
     //...
     
     #endif
     
这是为了避免大工程里cpp文件多次include 该头文件时不会出现 重引用的问题

但这里的取名PCA_H也是很讲究的，别和OpenCV 库里的PCA重了，重了之后自然会报一堆错，什么 InputArray没有定义啊，之类的

## 傻逼富强打印店
经常有傻逼病毒，autorun什么的，就是会把你的文件夹隐藏，再生成同名的exe.或快捷方式文件

解决方法如下

https://www.cnblogs.com/tlnshuju/p/7193740.html

再也不去那家傻逼打印店了

### 一般运行到一半不报错闪退都是因为 数组或vector下标越界，或者没有给它安排空间，没有size，resize等等

# 1.11
https://blog.csdn.net/p5deyt322jacs/article/details/80745723 AI,云计算

博学而笃志，切问而近思啊孩子

https://blog.csdn.net/xx1129244705/article/details/78036713 进程，并行，多进程


This

类的this指针，是该类的一个指针 

//用法

this-> 某函数();

# 1.13 
链表使用

https://blog.csdn.net/u011411195/article/details/51150102

Vector Swap 同类型向量交换

  // swap vectors
   #include <iostream>
   #include <vector>

    int main ()
    {
       std::vector<int> foo (3,100);   // three ints with a value of 100   这个构造方法也要会啊
       std::vector<int> bar (5,200);   // five ints with a value of 200

       foo.swap(bar);  // foo 和 bar 两个vector 交换

      std::cout << "foo contains:";
      for (unsigned i=0; i<foo.size(); i++)
         std::cout << ' ' << foo[i];
      std::cout << '\n';

      std::cout << "bar contains:";
      for (unsigned i=0; i<bar.size(); i++)
      std::cout << ' ' << bar[i];
      std::cout << '\n';
 
      return 0;
    }

Output:

foo contains: 200 200 200 200 200 

bar contains: 100 100 100 

## 写DXF文件
很重要啊孩子

https://blog.csdn.net/Augusdi/article/details/7493884

# 1.14
## AutoCAD重安装，之前手动卸载注册表没有删好

删除方法如下 2017/2018

https://jingyan.baidu.com/article/ea24bc39c54a73da62b3313b.html

## AutoDesk Recap点云显示测试，很炫酷
读取有问题

配准功能

http://help.autodesk.com/view/RECAP/2017/ENU/?guid=GUID-F863ED13-20A7-4873-AE42-2AAFDDF02295


## DLL动态链接库插件介绍
https://blog.csdn.net/roger_ranger/article/details/78279205

## AutoCad DXF 颜色
https://blog.csdn.net/wangjiwei2010/article/details/1245974

# 1.15

## C++ Pair 用法
https://www.cnblogs.com/lvchaoshun/p/7769003.html
## C++ Vector Insert 用法
https://www.cnblogs.com/cappuccino/p/3794698.html

# 1.19 
求你别把那丑陋的代码拿出去秀了，真的写得恶心

如何编译静态库lib 并链接使用

https://blog.csdn.net/u010335911/article/details/23474919?utm_source=blogxgwz3

### Cmake 出来的VS项目 会自动生成 三个Project

https://blog.csdn.net/sidely/article/details/52537488

一般由CMAKE构建的解决方案（Solution）中包含三工程（Project），分别是ALL_BUILD、ZERO_CHECK、INSTALL

ALL_BUILD只要编译这个工程，所有的工程均会编译；

ZERO_CHECK监视CMakeLists.txt文件的变化，一旦发生变化，它会告诉编译器重新构建整个工程环境。

INSTALL:将工程编译后生成的dll和exe等安装到指定目录中，具体安装位置和安装内容详见该工程的Build Event->Post-Build Event->Command Line。

ALL_BUILD 生成不了，导致别的工程也不能生成

https://blog.csdn.net/moonwindhui/article/details/45130801

将所要运行项目设成启动项 即可

### 不同版本的VS项目可能造成的问题

fatal error C1189: #error : The C++ Standard Library forbids macroizing keywords. Enable warning C4005 to find the forbidden macro.
最近在使用 VS2015 编译以前用VS2008的项目的时候，提示错误：fatal error C1189: #error :  The C++ Standard Library forbids macroizing keywords. Enable warning C4005 to find the forbidden macro.

解决方法：在项目的“预处理器定义”中增加 "_XKEYCHECK_H"

## C++ 学习
复制构造函数

用已有的对象来生成一个新对象

assert() 函数的使用

https://www.cnblogs.com/ggzss/archive/2011/08/18/2145017.html

### C++ 里的结构体其实就是一种简易的类，不仅可以有成员变量，也可以有成员函数 

### 联合体 
    Union markings
    {
       char grade;
       int score;
       bool pass;
    };

共用存储空间, 成绩只能有一种

### 枚举 
enum 

### 枚举类（强类型枚举）
enum class Type {General, Light, Medium, Heavy}

同 enum Type {General, Light, Medium, Heavy}  这种C继承来的简单枚举，默认类型为int

调用枚举对象时要用 Type::General 作用域限制

enum class Type: char {General, Light, Medium, Heavy}  枚举常量的类型可自定

:: 主要是控制作用域，在 C++里面

# 1.21
## 配准
### NDT
https://www.cnblogs.com/yhlx125/p/5749770.html
### G-ICP
https://www.cnblogs.com/yhlx125/p/5709157.html

# 1.22
## 编译时间过长的解决
https://blog.csdn.net/ugg/article/details/1489765

https://blog.csdn.net/amusi1994/article/details/53679140
## 用Cmake编译的步骤
Configure(VS 12 2013) ->  Generate  -> VS Project build
## #pragma Once vs #ifndef
https://blog.csdn.net/reasonyuanrobot/article/details/83858319

# 1.23 
## PDAL 库编译 失败

## CC插件
https://www.jianshu.com/p/e4b9d4c9360f

# 1.24
## XXXconfig.cmake文件
https://blog.csdn.net/historycomputer/article/details/59121420

## CC 插件 2次开发
看看自己的word文档

如何基于 QDummy_PLUGIN制作自己的PLUGIN

## 宇哥的Blog PCL+QT+VS配置
https://blog.csdn.net/qq_34719188/article/details/78961695

## Qmake生成 pro文件
使用qmake构建pro文件
在终端进入到你的插件的qSAF目录，执行：

qmake -project -r CMakeLists.txt
就会在qSAF目录下构建一个项目的pro文件。

# 1.25 
## 毕业设计思路确定

## 看看图优化和Vorining图分块

# 1.27
## 曾经遇到过的问题， PCL 版本问题， 某个函数不再用了 deprecated 
https://blog.csdn.net/wokaowokaowokao12345/article/details/51287011

方法，属性-> C/C++ 里面 ，把SDL检查改成否即可

# 2.1 
## 过完年了，准备开始学车了
## 还有任务准备做起来

## 利用控制TLS点云纠正ALS点云的数据质量的技术方案以及数据采集方案制定
### 1)	TLS 控制点云采集方案
	尽量均匀的300米左右一个控制点，共计30-50个（道路两侧均匀设站），尽量保证控制点云的精度优于5cm
### 2)	航带平差，得到精度报告（可用商业软件或者开源代码）
### 3)	利用精度报告结合GPS/IMU的精度推算设站位置
	规则格网的方式

	Vorinoi图，加权面积相似的方式
### 4)	根据TLS设站位置对ALS分块（是否需要从粗到精的分块，有待检验）
### 5)	基于改进GICP的ALS和TLS精配准
	先跑通GICP，并做测试，然后针对问题改进。可能的改进：

a)	根据粗糙度、距离、入射角等加权

b)	全局最优

c)	低重叠度问题

### 6)	误差改正模型
	暂时先考虑时变误差模型—改轨迹—重新解算点云

	参考文献

### 7)	全局最优的位置精度改正
	借鉴SLAM后端优化技术

	ALS和TLS对应点的拟合残差--数据项

	相邻ALS之间重叠区域对应点的拟合残--平滑项

	数据项和平滑项之间权值的自适应确定

### 8)	先找梁福逊要城区TLS和ALS做实验，测试GICP

## 刷Kaggle
https://blog.csdn.net/gh13uy2ql0N5/article/details/78293745

# 2.16
## 微分几何，流形
https://www.jianshu.com/p/0950e71274fd

## GICP blog
https://blog.csdn.net/xuyi1218037/article/details/84313750

## point-to-point , point-to-plane, point-to-line and plane-to-plane (GICP)
这些ICP变种都是只改了已知对应关系估计最优变换的部分，把优化函数残差和的残差之定义进行了改动

而对于求对应关系，为了效率，要使用KD-tree，延用了找最近点的方式

优化过程涉及非线性优化,有严密解也有数值解

### Closed Form
1.SVD

2.Unit Quaternions单位四元数

3.The ICP error function minimization via orthonormal matrices

4.Dual Quaternions

5.共轭梯度法 conjugate gradient

### 数值解法
1.LM算法 （Levenberg-Marquardt algorithm）

2.Jerbić, B., et al. (2015). "Robot Assisted 3D Point Cloud Object Registration." Procedia Engineering 100: 847-852.

3.点到面 线性最小二乘法
•Low, K.-L. (2004). "Linear Least-Squares Optimization for Point-to-Plane ICP Surface Registration."

## 非线性优化之 共轭梯度法
共轭梯度法（Conjugate Gradient）是介于最速下降法与牛顿法之间的一个方法，它仅需利用一阶导数信息，但克服了最速下降法收敛慢的缺点，又避免了牛顿法需要存储和计算Hesse矩阵并求逆的缺点，共轭梯度法不仅是解决大型线性方程组最有用的方法之一，也是解大型非线性最优化最有效的算法之一。 在各种优化算法中，共轭梯度法是非常重要的一种。其优点是所需存储量小，具有步收敛性，稳定性高，而且不需要任何外来参数。

https://blog.csdn.net/lusongno1/article/details/78550803

# 2.18
## 非线性优化 好帖
http://blog.sina.com.cn/s/blog_7445c2940102x3x4.html#commentComment

# 2.20
## g2o+VS13 配置
https://blog.csdn.net/xiaopihai1993/article/details/76644656

https://blog.csdn.net/aptx704610875/article/details/51245143

## 联系学车，毕设开题
## YAML 配置文件 C++
https://blog.csdn.net/firo_baidu/article/details/6843554

# 2.21 
## OpenMP 并行计算
https://blog.csdn.net/eric_e/article/details/79156504
