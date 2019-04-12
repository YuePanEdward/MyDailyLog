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

## 维诺图与德洛尼三角网
https://blog.csdn.net/kevin_darkelf/article/details/81455687

## Glog日志
https://www.cnblogs.com/zhoug2020/p/5884598.html

# 2.27 
## Coming back to study. No more vocation please.
## UTM (Universal Transverse Mecator) Projection 通用横轴墨卡托投影
Transverse 横向的，横轴的

## 相关介绍
https://blog.csdn.net/haima1998/article/details/82664781

北京54，西安80，wgs84坐标都是是大地坐标，也就是我们通常所说的经纬度坐标，但是它们基于的椭球体不同，我国当前的基本比例尺地形图都是基于北京54和西安80的，而GPS接受的定位数据是基于WGS84的。

### UTM是一种投影坐标，是将球面经纬度坐标经过投影算法转换成的平面坐标，即通常所说的XY坐标。

ARCGIS里面说的UTM WGS84是说来源是WGS84，然后经过UTM投影。

https://blog.csdn.net/uqocean/article/details/17690081 

   UTM (UNIVERSAL TRANSVERSE MERCARTOR GRID SYSTEM,通用横墨卡托格网系统) 坐标是一种平面直角坐标,这种坐标格网系统及其所依据的投影已经广泛用于地形图，作为卫星影像和自然资源数据库的参考格网以及要求精确定位的其他应用。

   在UTM系统中，北纬84度和南纬80度之间的地球表面积按经度6度划分为南北纵带(投影带)。从180度经线开始向东将这些投影带编号，从1编至60(北京处于第50带)。每个带再划分为纬差8度的四边形。四边形的横行从南纬80度开始。用字母C至X(不含I和O)依次标记(第X行包括北半球从北纬72度至84度全部陆地面积，共12度)每个四边形用数字和字母组合标记。参考格网向右向上读取。每一四边形划分为很多边长为1000 000米的小区，用字母组合系统标记。在每个投影带中，位于带中心的经线，赋予横坐标值为500 000米。对于北半球赤道的标记坐标值为0，对于南半球为10000000米，往南递减。
   
   大比例尺地图UTM方格主线间距离一般为1KM,因此UTM系统有时候也被称作方里格。因为UTM系统采用的是横墨卡托投影，沿每一条南北格网线(带中心的一条格网线为经线)比例系数为常数，在东西方向则为变数。沿每一UTM格网的中心格网线的比例系数应为0．99960(比例尺较小)，在南北纵行最宽部分(赤道)的边缘上，包括带的重叠部分，距离中心点大约363公里，比例系数为 1.00158。

   UTM投影全称为“通用横轴墨卡托投影”，是一种“等角横轴割圆柱投影”，【等角的，即投影后保角，和高斯-克鲁格投影的区别主要在于中央经线的比例系数】椭圆柱割地球于南纬80度、北纬84度两条等高圈，投影后两条相割的经线上没有变形，而中央经线上长度比0.9996。UTM投影是为了全球战争需要创建的，美国于1948年完成这种通用投影系统的计算。与高斯-克吕格投影相似，该投影角度没有变形，中央经线为直线，且为投影的对称轴，中央经线的比例因子取0.9996是为了保证离中央经线左右约330km处有两条不失真的标准经线UTM投影分带方法与高斯-克吕格投影相似，是自西经180°起每隔经差6度自西向东分带，将地球划分为60个投影带。 我国的卫星影像资料常采用UTM投影。
     
### 我国的UTM分带
https://blog.csdn.net/aganliang/article/details/83025326

### WGS84 经纬度（球）坐标 E，N --UTM Projection---> X,Y UTM WGS84 下的平面坐标
转换代码


# 3.9 
## 主要是模板类的学习

## 我也是醉了，这算什么呀，雅思6都考不到

模板类的注意点
https://blog.csdn.net/caoshangpa/article/details/53389234

注意了，模板类的声明和定义要放在一个文件里，否则会报LNK2001的链接错误

1. 一个类：

头文件用于保存类的声明；定义文件保存类的实现。

2. 分离编译模式：

允许在一个编译单元（.cpp文件）中定义函数、类型、类对象等，然后在另一个编译单元中引用它们。编译器处理完所有的编译单元后，链接器接下来会处理所有指向extern符号的引用（有时为缺省），从而生成单一可执行文件。

3. 模板类型：

模板类型不是一种实类型，它必须等到类型绑定后才能确定最终类型，所以在实例化一个模板时，必须要能够让编译器“看到”在哪里使用了模板，而且必须看到模板确切的定义，而不仅仅是它们的声明，都则不能顺利地产生编译代码。因此，标准会要求模板的实例化与定义体放到同一编译单元中。

4. 三种方法：

（1）模板的声明和定义都放置在同一个.h文件中（最好）：
 
（2）hpp文件

（3）也可以在main里直接include xxx.cpp

 ## 见上述网址

代码规范化要注意啊

天行健，君子以自强不息。
地势坤，君子以厚德载物。

# 3.16
## 马氏距离(Mahalanobis distance)介绍

马氏距离是由印度统计学家马哈拉诺比斯（P. C. Mahalanobis）提出的，表示数据的协方差距离。它是一种有效的计算两个未知样本集的相似度的方法。与欧氏距离不同的是它考虑到各种特性之间的联系（例如：一条关于身高的信息会带来一条关于体重的信息，因为两者是有关联的）并且是尺度无关的（scale-invariant），即独立于测量尺度。

https://www.cnblogs.com/DPL-Doreen/p/8183909.html

## vector的6种初始化方式
https://blog.csdn.net/veghlreywg/article/details/80400382

## 嵌套vector的初始化
vector< vector< int > > AIcards( 4, vector< int >( 13 ) );  4*13 的2维vector

# 3.18
## 智能指针的初始化一定要注意啊
https://blog.csdn.net/Sub_lele/article/details/75137252

XXXPtr yyy (new XXX());

# 3.25
## 之前的dll问题，排查
zlib.dll的问题

之后环境变量PATH一定要注意，别瞎配

打包的时候连通这些dll一起，放在同一目录下

你电脑上可以运行是因为环境变量里已经有了

如果不报缺少某dll的错，而是说无法运行，那就要注意还有可能是dll文件名字一样，但内容不同或版本不同，就像zlib.dll

## 使用GDAL的时候一个LNK2001的链接错误
https://blog.csdn.net/mandy_limin/article/details/52882843

# .hpp 文件
https://www.cnblogs.com/-Mr-y/p/7985537.html

还有要注意模板类的声明和定义要在同一个文件内，否则会报LNK2001


# 4.12 
刷leetcode啊伙计

今日leetcode 

感觉自己弱的像只咸鱼+菜鸡

## 2.ADD TWO NUMBERS

链表加法，别想复杂了，直接对位做加法运算，别先转成int在做，那样很容易overflow过2^32次方的

就用正常加法的思路，看有没有进位，进位只有0和1的

还有就是注意C++里指针的定义,PCL里也一样，都是 XXX*  xxx =new (XXX), pcl 人家也是 XXXPtr xxx=new (XXX)这样的，但赋另外一个指针的话可以直接 XXX* xxx =yyy； yyy也是另一个指针嘛， 还有指针如果赋值相等了意味着指向的东西就完全一样了，A，B两指针 A=B之后 *A怎么变， *B也跟着变的，因为它们指向的在内存里的地址就是一个了。 

## 14.Longest Common Prefix

这道题的话注意下

java里面求字符串中子字符串的索引位置的函数 string.indexOf(subindex) ，没找到返回-1，找到就在开头返回0

这里就有很多方法，可以顺序的一一比对，并更新当前的prefix

## 26. Remove Duplicates from Sorted Array
https://leetcode.com/problems/remove-duplicates-from-sorted-array/

这题很简单，注意两点，一种是vector删除元素的三种方法,pop_back()弹出栈尾的元素,erase(xxx.begin()+xx)迭代器法和remove(),前两种都是会同时改变vector的size的，而remove不会，啊

参见这个blog

https://blog.csdn.net/dongyanxia1000/article/details/52838922

https://blog.csdn.net/yockie/article/details/7859330

还有一点就是   
// Remember that vector.size() 's return value is size_t, which is a unsigned walue,which means when vector.size()==0, nums.size()-1 would overflow and be a very large value, which will cause a lot of problem. So you must cast nums.size() to integer and then run the code. 就是应对[]空向量的情况的，因为Leetcode 的OJ是会遍历所有的可能输入的，有一个有错你就凉凉，所以要注意啊

Leetcode加油刷，你还有可能进Momenta或百度地图

# 单元测试相关
https://www.cnblogs.com/cr330326/p/7388143.html

还是要努力刷Leetcode啊，然后看看宇哥的面试题

算法导论，计算机视觉，PRML等等书都要看起来，否则哪儿来长足的进步
