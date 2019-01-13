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
  std::vector<int> foo (3,100);   // three ints with a value of 100
  std::vector<int> bar (5,200);   // five ints with a value of 200

  foo.swap(bar);

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
