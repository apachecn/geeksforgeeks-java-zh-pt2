# Java 中的静态块和 main()方法

> 原文:[https://www . geesforgeks . org/static-block-and-main-method-in-Java/](https://www.geeksforgeeks.org/static-block-and-main-method-in-java/)

在 Java 中[静态块](https://www.geeksforgeeks.org/g-fact-79/)用于初始化静态数据成员。需要注意的重要一点是，在类加载时，静态块在主方法之前执行。

下面的例子很好地说明了这一点:

```
// Java program to demonstrate that static 
// block is executed before main()

class staticExample {

    // static block
    static
    {
        System.out.println("Inside Static Block.");
    }

    // main method
    public static void main(String args[])
    {
        System.out.println("Inside main method.");
    }
}
```

一个问题来自上面的例子:

**问题:**可以不声明 main()方法执行一个 Java 类吗？
**回答:**没有，因为 JDK 1.7 没有 main()方法是不可能执行任何 java 类的。但这是 JDK 1.6 之前的方法之一。
示例:

```
// The below code would not work in JDK 1.7
class staticExample {

    // static block execution without main method in JDK 1.6.
    static
    {
        System.out.println("Inside Static Block.");
        System.exit(0);
    }
}
```

产出:(JDK 1.6)

```
Inside Static Block.

```

但是从 JDK 1.7 开始，上面的代码给出了一个输出错误。

输出:

```
Error: Main method not found in class staticExample, please define the main method as:
       public static void main(String args[])
       or a JavaFX application class must extend javafx.application.Application

```