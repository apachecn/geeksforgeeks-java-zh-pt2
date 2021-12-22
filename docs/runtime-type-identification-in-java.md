# Java 中的运行时类型标识

> 原文:[https://www . geesforgeks . org/runtime-type-identificati on-in-Java/](https://www.geeksforgeeks.org/runtime-type-identification-in-java/)

Java 中的运行时类型标识可以定义为在运行时确定对象的类型。确定接受 java.lang 类型参数的方法的类型是极其重要的。与 C++不同，java 不支持运行时类型标识(RTTI)，但它提供了很少的方法来在运行时查找对象。

**Java 中关于运行时类型识别的一些要点如下:**

*   在运行时确定对象的类型不仅可以减少错误，还可以提高健壮性。
*   在将任何对象类型转换为另一种类型之前，避免运行时异常也很有用。
*   它用于在接受对象或任何接口等类型的方法上实现特定于类型的功能。

**Java . lang . object . getclass()**方法用于在运行时确定对象的类型。

**语法:**

```
public final Class getClass()
```

**返回类型:**返回代表该对象运行时类的类对象。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to determine Runtime type

import java.io.*;

public class Example1 {
    public static void main(String[] args)
    {
        // Creating the obj
        Object obj = new String("Learn_programming");

        Class abc = obj.getClass();

        // Print the class of obj
        System.out.println("Class of Object obj is : "
                           + abc.getName());
    }
}
```

**Output**

```
Class of Object obj is : java.lang.String

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to determine object class at run time 

import java.io.*;

public class Example2 {  
    public static void main(String[] args)   
    {   
      // create a new Integer
      Integer num = new Integer(100);

      // print num 
      System.out.println("" + num);

      // print the class of num
      System.out.println("" + num.getClass());

    }   
}  
```

**输出:**

```
100
class java.lang.Integer
```