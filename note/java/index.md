# Java 

- [Java 基础](https://www.liaoxuefeng.com/wiki/1252599548343744/1255883772263712)

## Java 简介

Java介于编译型语言和解释型语言之间。


Java EE 包含 Java SE, Java SE 包含 Java ME

Java ME就和Java SE不同，它是一个针对嵌入式设备的“瘦身版”，Java SE的标准库无法在Java ME上使用，Java 

Java SE的核心技术是基础.



JDK：Java Development Kit
JRE：Java Runtime Environment

JRE就是运行Java字节码的虚拟机

JDK除了包含JRE，还提供了编译器、调试器等开发工具。



## Hello world 

Java程序总是从main方法开始执行


先用javac把Hello.java编译成字节码文件Hello.class，然后，用java命令执行这个字节码文件



## 基础

### 变量和数据类型

变量分为两种：基本类型的变量和引用类型的变量。


注意char类型使用单引号'，且仅有一个字符，要和双引号"的字符串类型区分开。


引用类型最常用的就是String字符串：

```
String str = "hello";
```

引用类型的变量类似于C语言的指针，它内部存储一个“地址”，指向某个对象在内存的位置

**常量**
定义变量的时候，如果加上final修饰符

```
final double PI = 3.1415926;
```
常量在定义时进行初始化后就不可再次赋值，再次赋值会导致编译错误。

**var关键字**
用于省略变量类型

```
StringBuilder sb = new StringBuilder();

var sb = new StringBuilder();
```

** 变量的作用范围**

{} 块级作用域


