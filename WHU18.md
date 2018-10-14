# Coming back to WHU

# Come on, fight for your dream.

# 9.28

## int main (int argc, char argv[]) 含义

argc：命令行总的参数的个数,即argv中元素的格式。

* argv[ ]: 字符串数组,用来存放指向你的字符串参数的指针数组,每一个元素指向一个参数

* argv[0]:指向程序的全路径名

* argv[1]:指向在DOS命令行中执行程序名后的第一个字符串。

* argv[2]:指向第二个字符串

# 10.8

## Please work hard, for your final dream.
## Don't be disturbed by those girls.


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
    
    
