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

### 重要

还有就是注意C++里指针的定义,PCL里也一样，都是 XXX*  xxx (new XXX), pcl 人家也是 XXXPtr xxx (new XXX)这样的，但赋另外一个指针的话可以直接 XXX* xxx =yyy； yyy也是另一个指针嘛， 还有指针如果赋值相等了意味着指向的东西就完全一样了，A，B两指针 A=B之后 *A怎么变， *B也跟着变的，因为它们指向的在内存里的地址就是一个了。 

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

# 4.13
## 注意下链表啊，你刷leetcode刷出个翔啊

https://www.cnblogs.com/en-heng/p/6385910.html

# 4.14
## 1.写switch case语句不加break会怎样。

switch case语句犯得错误：

会犯这种错误，都是基础不牢固导致的。但是这样的错误却花费了我数小时去debug.想来真是很让人郁闷。

看一段代码:（不想看代码直接看后面总结）
          
          private void arrange() {
                 switch (direction) {
                     case 'U': 
                     case 'R':
                     case 'D':
                     case 'L':
          
           }
           
### 在这个语句中，如果direction=U。那么四个case语句都将执行。如果direction=R。将执行剩下三个语句。原因是switch语句原理是跳转到caseX位置执行剩下的语句，直到最后或者遇见break为止。

因此在每一条语句最后+break即可。

         private void arrange() {
             switch (direction) {
                  case 'U':  break；
                  case'R':   break；
                  case'D':  break；
                  case'L':   break；
          
            }
            
            
这样就能，每一个direction执行一步操作。

当然还有 别的用法，比如一个direction，让他可以执行两条或者3条操作这种。

### 总结：
switch语句原理是跳转到caseX位置执行剩下所有的语句（包括其他case里面的），直到最后或者遇见break为止。因此在每一条语句最后+break即可。
因此不加break的话将会执行跳转到的case本身以及以下所有的语句。

# 4.15
真的要开始认真努力了。

守时，自律，自尊也要自信。同时多照顾别人，别变成那个愚蠢的自己。

永远别怂，心态要好

## 刷leetcode
经典问题 #70 Climbing Stairs

解法许多，如下 https://leetcode.com/problems/climbing-stairs/solution/

注意它就是个菲布纳基数列，同时也可以用动态规划的思路来解。

    dp[i]=dp[i-1]+dp[i-2]  
    //到达i step有两种方法: 1. 到 i-1 step，再爬1 step  2. 到 i-2 step,再爬2 steps.
    //到达i的方法数量等于 这两种情况的方法数之和
    

# 4.16
科二顺利过了，激动！

努力，fighting gold.

## 动态规划 Dynamic Programming
https://blog.csdn.net/iva_brother/article/details/84037050

## 分治法 Divide and Conquer 
https://blog.csdn.net/xlinsist/article/details/79198842

## 贪心算法

## 看看算法导论呢孩子

# 4.17
## 算法导论 分治法部分 
Divide -> Conquer -> Combine (In a Recursion Scheme)

几个例子，归并排序 和 最大子数组，都是 O(nlogn)的复杂度，比brute force的O(n^2)要好

递归式与主方法Master Method

## 二叉搜索树 BST
前中后序遍历别忘了

https://blog.csdn.net/qq_33243189/article/details/80222629

https://www.cnblogs.com/CongLollipop/p/6858260.html

## 五大算法

### 分治法
https://www.cnblogs.com/steven_oyj/archive/2010/05/22/1741370.html

### 动态规划
https://www.cnblogs.com/steven_oyj/archive/2010/05/22/1741374.html

# 4.18
## 日常刷leetcode
### 判断树是否轴对称，两种方法(DFS recursion(stack)法 和 BFS 的iterative(queue)法，树类的题目基本都可以用这两种方法，只是递归的都不太好想
https://leetcode.com/problems/symmetric-tree/solution/

 //For C++ container queue, the methods are push , pop and front;[Not push_back or pop_back, and front is the first element in the queue]

### 从已有vector里取出子列出来的方法

     vector<int> Left (myArray.begin(),myArray.begin()+mid_index);
     vector<int> Right(myArray.begin()+mid_index,myArray.end());

# 4.19
## 日常刷leetcode
别把异或(XOR)给忘了，异或就是一种半加(即不带进位的二进制加法） 
      
     // 异或运算 ， A 和 B 相等则结果为0， 不等则结果为1 
     1 XOR 0 = 1 
     0 XOR 1 = 1 
     1 XOR 1 = 0 
     0 XOR 0 = 0
     // 其他
     A XOR 0 = A
     A XOR A = 0

而且满足交换律

看看这道Single Number里面的方法四，也太秀了，把整个数组依次异或，重复出现两次的数都消掉了。最后就剩下落单的那个 B XOR 0 = B，也就是最后输出落单数就是连续异或的结果

https://leetcode.com/problems/single-number/submissions/

## C++ 其他几个和Hashtable 相关的容器
set   unordered_set

        unordered_set<int> s;
        for(int num : nums)
        {
            if(s.count(num))  s.erase(num);
            else              s.insert(num);
        }
        return *s.begin();
      
## 别忘了这个常识了
i++ （先取值，再自增） 和 ++i  （先自增，再取值）

# 4.22
## CC插件相关
### 示例代码：
1.qSAF： https://github.com/huihut/qSAF

2.MeshIO： https://github.com/asmaloney/MeshIO

3.Qt UI工程：https://github.com/huihut/CloudCompare-Qt

4.CC已有插件源码

5.其他几个示例代码：海量点云八叉树，基于区域生长的分割

### 教程：
1.插件框架： https://blog.huihut.com/2017/04/27/CloudCompareSAFPlugin_1_Framework/

2.数据结构： https://blog.huihut.com/2017/04/27/CloudCompareSAFPlugin_2_DataStructure/

3.算法实现： https://blog.huihut.com/2017/04/27/CloudCompareSAFPlugin_3_Algorithm/

4.CC插件初探：https://www.cnblogs.com/yhlx125/p/5425040.html

## C++自带排序函数 sort

          sort(nums.begin(),nums.end()); // Sort的用法要注意啊（内核是红黑树与快排）
         //sort 对数组，对vector容器都可以用，用法也类似
         //vector v 就是 sort(v.begin(),v.end());
         //array a[K] 就是 sort(a,a+K);

## CloudCompare二次开发 新
https://www.cnblogs.com/z-web-2017/p/9688564.html#4172233

https://www.cnblogs.com/z-web-2017/p/10350451.html

# 4.24
## Reverse a Linked List
两种方法，迭代法和递归法

感觉递归法很难懂 https://leetcode.com/problems/reverse-linked-list/submissions/

# 4.25
## 准备面试
### 各类激活函数及其区别
https://blog.csdn.net/lilu916/article/details/77822309

    Sigmoid 0~1 logistic 
    tanh -1~1
    Relu max(0,x)

### 迁移学习
https://blog.csdn.net/u010159842/article/details/79202107

用一些和目标问题类似的通用的预训练好的网络，只训练后面几层，或者微调前面的神经元。这样可以减少所需的训练样本数量，而起到不错的效果。

### 正则化 
https://blog.csdn.net/gshgsh1228/article/details/52199870/  正则化提供先验，防止过拟合

https://blog.csdn.net/w5688414/article/details/78046960 正则化L1，L2范数

### 增强学习 RL
试错与延迟反馈

agent 面对environment的action 不同状态state下执行不同操作action会有不同的reward

对于最终的reward通过动态规划（贝尔曼方程来摊牌到每个action上），进行学习

如Flappy Bird 和下棋

https://blog.csdn.net/hellocsz/article/details/80724225

### RNN
https://blog.csdn.net/zhaojc1995/article/details/80572098

### 并发，并行 Concurrecy 与多线程

   所有的并发处理都有排队等候，唤醒和执行这三个步骤，所以并发是宏观的观念，在微观上他们都是序列被处理的，只不过资源不会在某一个上被阻塞（一般是通过时间片轮转），所以在宏观上多个几乎同时到达的请求同时在被处理。如果是同一时刻到达的请求也会根据优先级的不同，先后进入队列排队等候执行。

   并发与并行是两个既相似但是却不相同的概念：

   并发性：又称共行性，是指处理多个同时性活动的能力，。

   并行：指同时发生两个并发事件，具有并发的含义。并发不一定并行，也可以说并发事件之间不一定要同一时刻发生。 

   并发的实质是一个物理CPU（也可以是多个物理CPU）在若干个程序之间多路复用，并发性是对有限物理资源强制行使 多用户共享以提高效率。

   并行指两个或两个以上事件或活动在同一时刻发生，在多道程序环境下，并行使多个程序同一时刻可在不同CPU上同时执行。    

   并发是在同一个cpu上同时（不是真正的同时，而是看来是同时，因为CPU要在多个程序之间切换）运行多个程序。

   并行是每一个CPU运行一个程序。

   打个比方：并发就像一个人（CPU）喂两个小孩（程序）吃饭，表面上是两个小孩在吃饭，实际是一个人在喂。

    并行就是两个人喂两个小孩子吃饭
    
### GAN 生成式对抗网络
https://www.cnblogs.com/xiaowangzi1987/p/6706416.html

一个生成网络，一个分类网络（二分，是真实的还是生成的假图片），左右互博，直到分类网络分不清为止结束，这时候生成网络就足够稳健了

### 条件随机场CRF，隐含马尔可夫模型HMM
https://blog.csdn.net/dcx_abc/article/details/78319246 

作图像分类的时候不是只看单张，而是考虑图像序列和它们之间的关系

### 重载和重写的区别 （这都不会是没公司会要你的）
https://www.cnblogs.com/upcwanghaibo/p/6527354.html

Overload 重载， 变量列表改变，但函数名相同

Override 重写， 继承中的多态性， 父类与子类同一个函数，子类对父类的函数进行重写，来实现多态

### 多态性
多态性是面向对象编程的一种特性，和方法无关，

简单说，就是同样的一个方法能够根据输入数据的不同，做出不同的处理，即方法的重载——有不同的参数列表（静态多态性）

而当子类继承自父类的相同方法，输入数据一样，但要做出有别于父类的响应时，你就要覆盖父类方法，

即在子类中重写该方法——相同参数，不同实现（动态多态性）

### OOP三大特性：继承，多态，封装，很关键啊

# 4.29
你还是太菜了，没公司要你，还是要努力啊

实力不够啊就是。。。唉

## 单线与多线激光雷达的不同 （对于移动测量）
### 多线 如VLP16线，一般会水平摆放，转完一圈（转速比较慢）会传输一次数据，就是一帧周围的点云，故可能会导致运动畸变（在转的过程中载体也在运动了，而又是在转完后才解算数据，就是对所有点云都统一加了转完时刻的运动量 r(t1)，而其实在转一圈的时间里，运动量是从0到统一加的那个数的r(t) t=t0~t1，由此造成了所谓的运动畸变 dr(t)=r(t1)-r(t)，即t0时最大，t1时没有。 同时，帧与帧之间是有重叠的。用其他传感器提供的运动估计作初值进行配准可以精化运动估计。
### 而单线激光雷达，由载体的运动来实现空间的扫描。虽然精度和VLP的差不多，但转速快，转一圈算一条扫描线，由于是倾斜摆放，没有所谓帧的概念，即扫描线与扫描线之间理论上是没有重叠的。由于转的很快，所以运动畸变比较小，整体精度会高一点。

## LOAM 算法精讲 （重要）
https://blog.csdn.net/liuyanpeng12333/article/details/82718277
### 算法架构
和源码中代码构架一样，激光里程计主要分四部分完成。首先是获得激光雷达坐标系下的点云数据P^，然后把第k次扫描获得的点云组成一帧数据Pk。然后将Pk在两个算法中进行处理，也就是上面Liar Odometry节点和Lidar Mapping节点。Liar Odometry节点的作用是获取两帧连续点云数据间的运动，估计出来的运动用于去除Pk中的运动畸变。这个节点执行的频率为10Hz，作用相当于scan-to-scan匹配获得粗糙的运动估计用于去除匀速运动造成的运动畸变，并将处理后的结果给了Lidar Mapping节点做进一步处理。Lidar Mapping节点使用地图去匹配和注册没有畸变的点云数据以1Hz的频率。最后由Transform integration节点接收前面两个节点输出的Transform信息并将其进行融合处理以活动频率为10Hz的Transform信息即里程计。

### 这里主要就是层次化的进行配准嘛，高频(10Hz)的ICP作scan-to-scan registration，把相邻帧配起来【这就有点问题了，原来是运动畸变的，还是刚性配准吗？】，然后用相邻帧配准的运动估计来改正运动畸变，此即为Lidar Odometery, 然后这样用Lidar Odomtery做10帧左右把10帧融合成一个子图Submap,然后再过10帧，再出来个Submap,用低频(1Hz)的ICP来进行Map-to-Map的配准，来修正前面scan-to-scan的累积误差，再来输出地图。（具体咋搞啊）
### 也就是高频低精度与低频高精度之间的一个融合

### 如何高效完成scan-to-scan matching
提关键点

点云曲率计算：邻域PCA里  最小特征值/（三个特征值之和）

# 5.5 
莫名拿到Sensetime intern offer,要努力啊
## Robot state estimation 
Gaobao 

https://www.cnblogs.com/gaoxiang12/p/5560360.html

## MMT oral preparation

## RTabMap思想
​ 提供一个与时间和尺度无关的基于外观的定位与构图解决方案。 
​ 针对解决大型环境中的在线闭环检测问题。

思想
​ 为满足实时性的一些限制，闭环检测是仅仅利用有限数量的一些定位点，同时在需要的时候又能够访问到整个地图的定位点。当地图中定位点的数目使得找到定位匹配的时间超过某个阀值时，RTAB-MAP就将WM(Working Memory)中不太可能形成闭环的定位点转移到LTM（Long-Term Memory）中，这样这些被转移的位置点就不参与下次闭环检测的运算。当一个闭环被检测到时，其领接定位点又能够重新的从LTM中取回放入WM中，用于将来的闭环检测。

​ 由于LTM中的定位点并不参与闭环检测，因此选择WM中的哪些定点转移到LTM中非常重要。

​ rtab-map的思想是：假设更频繁的被访问的定位点比其他的定位点更易于形成闭环。这样一个定位点被连续访问的次数就可以用来衡量其易于形成闭环的权重。当需要从WM转移定位点到LTM中时，优先选择具有最低权重的定位点。如果具有最低权重的定位点又有多个时，优先选择被存储时间最长的那一个。

​ STM(Short-Term Memory)用于观察连续图像在时间上的相似度，并依此更新定位点的权重。

​ WM用于检测定位点在空间上的闭环假设。

​ RTAB-MAP闭环检测时并没有使用STM中的定位点，因为多数情况下，最后获取的定位点大多与其最近的定位点相似。

​ STM的存储量大小T取决于机器人的速度和定位点获取的频率，定位点数量达到t时，在STM中存储时间最长的定位点就被移动到WM中。

​ RTAB-Map用离散贝叶斯过滤器来估计形成闭环的概率，将新的定位点与存储在WM中的定位点进行比较。当发现新旧定位点之间有高概率形成闭环时，一个闭环就被检测到了，新旧定位点也就被链接在一起。有两个关键个步骤，一个是“取回”:对于具有形成闭环概率最高的那个定位点，将它的那些没有在WM中的领接定位点，重新从LTM中取出放回到WM中。第二个步骤叫做“转移”:当闭环检测的处理时间超过阀值,具有最低权重的定位点中，存储时间最长的将被转移到LTM中，被转移的定位点的数量取决于当前依赖循环中的WM存储的定位点的数量。



A. 定位点创建 Location Creation
​ 使用词袋法创建图像的签名，一幅图像的签名由视觉词典中的词的集合表示，是在线增量式创建的。

优点：选择增量式的创建方法，而不是采用预先训练号的词典，好处在于针对一个特定的环境不需要与训练过程。

词袋方法： 
第一步：利用SURF算法从不同类别的图像中提取视觉词汇向量，这些向量代表的是图像中局部不变的特征点； 
第二步：将所有特征点向量集合到一块，利用K-Means算法合并词义相近的视觉词汇，构造一个包含K个词汇的单词表； 
第三步：统计单词表中每个单词在图像中出现的次数，从而将图像表示成为一个K维数值向量

​ 基于opencv从图像中提取SURF特征(阀值超过Tresponse)来得到视觉单词。

注意:当提取到的特征的数目很少时（小于阀值Tbad）被认为是一个很差的签名，将不会被用于闭环检测。比如室内一堵白墙的图像。

​ 量化处理（找到词典中已有单词之间的匹配），rtab-map中采用最近邻和次近邻的比率NNDR,如果一个特征到最近邻的距离比到次近邻的距离的Tnndr倍药效，那么这个特征就能够被其最近邻的特征单词所表示。由四个随机化的kd-tree(FLANN)构成的分类森林来提高最近邻匹配的速率。kd-tree的构建是基于分层k-means聚类的，这样可以减低创建树的时间。

​ 这样一个定位点Lt就可以用签名Zt和时间索引t来创建，初始权重0，并与Lt-1在图中创建一个时间上的双向链接。


B. 权值更新 Weight Update
​ 为了更新获取到的定位点的权重，将Lt和STM中的最后一个定位点进行比较，相似度s通过（1）式来衡量



Npair表示定位点签名间匹配上的单词对的数量，Nzt与Nzc分别对应签名Zt与Zc的总单词数目。如果s超过固定的相似度阀值Tsimilarity,则将被比较的定位点Lc被融合到Lt中。融合后的签名中只保存来自Zc的单词，二词典中新增的来自Zt的单词会被删除：Zt被清空，将Zc复制到Zt中。

​ 最后Lt的权重设置为Lc的权重再加1，而且Lc的邻接和闭环链接重新链接到Lt,Lc则从STM中删除。

C. 贝叶斯过滤器更新 Bayesian Filter Update
​ 作用：估计当前定位点Lt和存储在WM中的定位点形成闭环的概率来记录闭环假设。

D. 闭环假设选择 Loop Closure Hypothesis Selection
​ 归一化后如果p比设定的闭环阀值Ttop小，那么p中具有概率最大值的闭环假设St=i就被认为是成立的。当一个闭环假设成立时，新的定位点Lt就与旧的定位点Li之间就建立了闭环链接：Lt的权重更新为原来的权重加上Li的权重，Li的权重设置为0，添加到Li到Lt的闭环链接。

E.取回 Retrieval
​ 闭环检测完成后，具有形成闭环概率最高的定位点的那些没在WM中的邻接定位点，会重新从LTM取回到WM中。

 
​ 注意：由于数据库中加载定位点是很消耗时间的，因此一次循环最多取回两个定位点（在C中定义的邻接范围内）。当超过两个定位点可以被取回时，时间上邻接的定位给点优先于在空间上的邻接定位点。

F. 转移Transfer
​ 当处理一帧图像的时间超过Ttime的时候,具有最低权重的定位点中，存储时间最长的将被转移到LTM中。

注意为了使离散贝叶斯过滤器能够合理的估计闭环假设，具有最高闭环假设定位点的邻接定位给点是不允许被转移的。



Ttime是通过实验经验来设置的，较高值的Ttime意味着更多的定位点会存储在WM中，这样更多的闭环假设能够被保存起来，也就更好的代表了整个环境。

因为rtab-map中计算时间代价最好的步骤是创建kd-tree,因此处理获取的每一帧图像的时间可以通过改变词典的大小来限制管理，词典的大小也间接影响了WM的大小。
 
 # 5.8
 MMT会议结束
 
 抓紧搞定毕设，马上要商汤实习了。还有个图森的面试。加油~
 
 ## 再看地图投影
 
 https://www.cnblogs.com/rainbow70626/p/4379615.html  
 
 超级好文啊
 
UTM是一种“等角横轴割圆柱投影”，椭圆柱割地球于南纬80度、北纬84度两条等高圈，投影后两条相割的经线上没有变形，而中央经线上长度比0.9996。UTM投影是为了全球战争需要创建的，美国于1948年完成这种通用投影系统的计算。

与高斯-克吕格投影相似，该投影角度没有变形，中央经线为直线，且为投影的对称轴，中央经线的比例因子取0.9996是为了保证离中央经线左右约330km处有两条不失真的标准经线。

### 多种坐标系，主要是工程坐标系啊，要注意好，投影面高程也是一个变量啦
http://www.360doc.com/content/18/0823/12/1302411_780572792.shtml

### 好文，有任意投影面高程 的投影坐标转换公式
https://wenku.baidu.com/view/2823d51cb7360b4c2e3f64dc.html

# 6.17
Long time no see, dude.

### Ubuntu终端Terminal常用快捷键

    快捷键 功能 
    Tab 自动补全 
    Ctrl+a 光标移动到开始位置 
    Ctrl+e 光标移动到最末尾 
    Ctrl+k 删除此处至末尾的所有内容 
    Ctrl+u 删除此处至开始的所有内容 
    Ctrl+d 删除当前字符 
    Ctrl+h 删除当前字符前一个字符 
    Ctrl+w 删除此处到左边的单词 
    Ctrl+y 粘贴由 Ctrl+u ， Ctrl+d ， Ctrl+w 删除的单词 
    Ctrl+l 相当于clear，即清屏 
    Ctrl+r 查找历史命令 
    Ctrl+b 向回移动光标 
    Ctrl+f 向前移动光标 
    Ctrl+t 将光标位置的字符和前一个字符进行位置交换 
    Ctrl+& 恢复 ctrl+h 或者 ctrl+d 或者 ctrl+w 删除的内容 
    Ctrl+S 暂停屏幕输出 
    Ctrl+Q 继续屏幕输出 
    Ctrl+Left-Arrow 光标移动到上一个单词的词首 
    Ctrl+Right-Arrow 光标移动到下一个单词的词尾 
    Ctrl+p 向上显示缓存命令 
    Ctrl+n 向下显示缓存命令 
    Ctrl+d 关闭终端 
    Ctrl+xx 在EOL和当前光标位置移动 
    Ctrl+x@ 显示可能hostname补全 
    Ctrl+c 终止进程/命令 
    Shift +上或下 终端上下滚动 
    Shift+PgUp/PgDn 终端上下翻页滚动 
    Ctrl+Shift+n 新终端 
    alt+F2 输入gnome-terminal打开终端 
    Shift+Ctrl+T 打开新的标签页 
    Shift+Ctrl+W 关闭标签页 
    Shift+Ctrl+C 复制 
    Shift+Ctrl+V 粘贴 
    Alt+数字 切换至对应的标签页 
    Shift+Ctrl+N 打开新的终端窗口 
    Shift+Ctrl+Q 管壁终端窗口 
    Shift+Ctrl+PgUp/PgDn 左移右移标签页 
    Ctrl+PgUp/PgDn 切换标签页 
    F1 打开帮助指南 
    F10 激活菜单栏 
    F11 全屏切换 
    Alt+F 打开 “文件” 菜单（file） 
    Alt+E 打开 “编辑” 菜单（edit） 
    Alt+V 打开 “查看” 菜单（view） 
    Alt+S 打开 “搜索” 菜单（search） 
    Alt+T 打开 “终端” 菜单（terminal） 
    Alt+H 打开 “帮助” 菜单（help） 
    另外一些小技巧包括：在终端窗口命令提示符下，连续按两次 Tab 键、或者连续按三次 Esc 键、或者按 Ctrl+I 组合键，将显示所有的命令及工具名称。Application 键即位置在键盘上右 Ctrl 键左边的那个键，作用相当于单击鼠标右键。

### Cmakelist

### Some kind of error  “undefined reference to XXX
Linux下编译程序时，经常会遇到“undefined reference to XXX” 报错，

这里总结一些可能的原因和解决方案，给需要的朋友：

 

说道undefined reference error，先提一下Linux gcc链接规则：

 

链接的时候查找顺序是:

 

    -L 指定的路径, 从左到右依次查找
    由 环境变量 LIBRARY_PATH 指定的路径,使用":"分割从左到右依次查找
    /etc/ld.so.conf 指定的路径顺序
    /lib 和 /usr/lib (64位下是/lib64和/usr/lib64)

动态库调用的查找顺序:

 

    ld的-rpath参数指定的路径, 这是写死在代码中的
    ld脚本指定的路径
    LD_LIBRARY_PATH 指定的路径
    /etc/ld.so.conf 指定的路径
    /lib和/usr/lib(64位下是/lib64和/usr/lib64)

一般情况链接的时候我们采用-L的方式指定查找路径, 调用动态链接库的时候采用LD_LIBRARY_PATH的方式指定链接路径.

另外注意一个问题,就是只要查找到第一个就会返回,后面的不会再查找. 比如-L./A -L./B -lx 在A中有libx.a B中有libx.a和libx.so, 这个时候会使用在./A的libx.a 而不会遵循动态库优先的原则,因为./A是先找到的,并且没有同名动态库存在

 

对于动态链接库，实际的符号定位是在运行期进行的．在编译.so的时候，如果没有把它需要的库和他一起进行联编，比如libx.so 需要使用uldict, 但是忘记在编译libx.so的时候加上-luldict的话，在编译libx.so的时候不会报错，因为这个时候libx.so被认为是一个库，它里面存在一些不知道具体实现的符号是合法的，是可以在运行期指定或者编译另外的二进制程序的时候指定．

如果是采用　g++ -Lpath -lx 的方式进行编译，链接器会发现所需要的uldict的符号表找不到从而报错，但是如果是程序采用dlopen的方式载入，由于是运行期，这个程序在这个地方就直接运行报错了．另外还有一种情况就是一个对外的接口在动态库中已经声明定义了，但是忘记实现了，这个时候也会产生类似的错误．

如果在运行期报出这样的错误，就要注意是否是由于某些库没有链接进来或者某些接口没有实现的原因产生


 

有了上述基础，不难看出，undefined reference error错误的原因是：

 没有指定对应的库（.o/.a/.so） 使用了库中定义的实体，但没有指定库（-lXXX）或者没有指定库路径（-LYYY），会导致该错误,
 连接库参数的顺序不对 在默认情况下,对于-l 使用库的要求是越是基础的库越要写在后面,无论是静态还动态
    gcc/ld 版本不匹配 gcc/ld的版本的兼容性问题,由于gcc2 到 gcc3大版本的兼容性存在问题(其实gcc3.2到3.4也一定程度上存在这样的问题) 当在高版本机器上使用低版本的机器就会导致这样的错误, 这个问题比较常见在32位的环境上, 另外就在32位环境不小心使用了64位的库或者反过来64位环境使用了32位的库.
    C/C++相互依赖和链接 gcc和g++编译结果的混用需要保证能够extern "C" 两边都可以使用的接口,在我们的64位环境中gcc链接g++的库还需要加上 -lstdc++,具体见前文对于混合编译的说明
    运行期报错 这个问题基本上是由于程序使用了dlopen方式载入.so, 但.so没有把所有需要的库都链接上,具体参加上文中对于静态库和动态库混合使用的说明

## 学习 vim， tmux, CMakeLists.txt, gdb


## 编译器版本问题
### 切换gcc，g++版本
https://my.oschina.net/u/2306127/blog/538139

注意了，依赖库编译时的编译器版本得和之后编译工程时的编译器版本一样，否则会出很多问题


## libuuid version's problem

### undefined reference to uuid_generate@UUID_1.0'
### undefined reference touuid_unparse_lower@UUID_1.0

//usr/lib/x86_64-linux-gnu/libSM.so.6: undefined reference to uuid_generate@UUID_1.0'
//usr/lib/x86_64-linux-gnu/libSM.so.6: undefined reference touuid_unparse_lower@UUID_1.0’

The system has two libuuid:
1) /lib/x86_64-linux-gnu/libuuid.so.1.3.0
2) /usr/local/lib/libuuid.so.1.0.0

Try to Change:
ldd //usr/lib/x86_64-linux-gnu/libSM.so.6
libuuid.so.1 => /usr/local/lib/libuuid.so.1 (0x00007f9bfb37e000)

### sudo ln -sf /lib/x86_64-linux-gnu/libuuid.so.1.3.0 /usr/local/lib/libuuid.so.1
