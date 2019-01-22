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
## 用Cmake编译的步骤
Configure(VS 12 2013) ->  Generate  -> VS Project build
