## C++ function with default value
声明的时候 要写默认值

而定义的时候不允许出现默认值

如下

```
　void point(int=3,int=4)； //声明中给出默认值
　　　　void point(intx，inty) //定义中不允许再给出默认值
　　　　{
　　　　　cout <<x<<endl；
　　　　　cout <<y<<endl；
　　　　}
```
