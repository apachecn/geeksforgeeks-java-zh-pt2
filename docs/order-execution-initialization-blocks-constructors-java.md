# Java 中初始化块和构造函数的执行顺序

> 原文:[https://www . geesforgeks . org/order-execution-initialization-blocks-constructors-Java/](https://www.geeksforgeeks.org/order-execution-initialization-blocks-constructors-java/)

**先决条件:** [静态块](https://www.geeksforgeeks.org/g-fact-79/)[初始化器块](https://www.geeksforgeeks.org/g-fact-26-the-initializer-block-in-java/)[构造器](https://www.geeksforgeeks.org/constructors-in-java/)
在 Java 程序中，可以对方法、构造器和初始化块进行操作。
**实例初始化块** : IIB 用于初始化实例变量。iib 在构造函数之前执行。每次创建类的对象时，它们都会运行。
**初始化器块:**包含每当创建实例时总是执行的代码。它用于声明/初始化类的各种构造函数的公共部分。
**构造函数:**用于初始化对象的状态。与方法一样，构造函数也包含在对象创建时执行的语句(即指令)的集合。

**Java 中初始化块和构造函数的执行顺序**

1.  每当首次在 JVM 中加载类时，静态初始化块都会运行
2.  [初始化块](https://www.geeksforgeeks.org/g-fact-26-the-initializer-block-in-java/)按照它们在程序中出现的相同顺序运行。
3.  [实例初始化块](https://www.geeksforgeeks.org/instance-initialization-block-iib-java/)在初始化类时和调用构造函数之前执行。它们通常放置在大括号内的构造函数之上。

```java
// Java code to illustrate order of
// execution of constructors, static
// and initialization blocks
class GFG {

    GFG(int x)
    {
        System.out.println("ONE argument constructor");
    }

    GFG()
    {
        System.out.println("No  argument constructor");
    }

    static
    {
        System.out.println("1st static init");
    }

    {
        System.out.println("1st instance init");
    }

    {
        System.out.println("2nd instance init");
    }

    static
    {
        System.out.println("2nd static init");
    }

    public static void main(String[] args)
    {
        new GFG();
        new GFG(8);
    }
}
```

**输出**

```java
1st static init
2nd static init
1st instance init
2nd instance init
No  argument constructor
1st instance init
2nd instance init
ONE argument constructor
```

**注意:**如果有两个或多个静态/初始化器块，那么它们将按照在源代码中出现的顺序执行。

现在，预测以下程序的输出-

```java
// A tricky Java code to predict the output
// based on order of 
// execution of constructors, static 
// and initialization blocks
class MyTest {
    static
    {
        initialize();
    }

    private static int sum;

    public static int getSum()
    {
        initialize();
        return sum;
    }

    private static boolean initialized = false;

    private static void initialize()
    {
        if (!initialized) {
            for (int i = 0; i < 100; i++)
                sum += i;
            initialized = true;
        }
    }
}

public class GFG {
    public static void main(String[] args)
    {
        System.out.println(MyTest.getSum());
    }
}
```

输出:

```java
9900

```

**说明:**

*   初始化函数中的循环从 0 到 99。考虑到这一点，您可能会认为该程序会打印从 0 到 99 的数字总和。因此总和是 99 × 100 / 2，即 4950。然而，该项目却不这么认为。它打印 **9900** ，足足是这个值的两倍。
*   为了理解它的行为，让我们追踪它的执行。GFG.main 方法调用 MyTest.getSum .在执行 getSum 方法之前，VM 必须初始化类 MyTest。类初始化按照静态初始化在源中出现的顺序执行静态初始化。
*   MyTest 类有两个静态初始化器:类顶部的静态块和初始化的静态字段的初始化。该块首先出现。它调用 initialize 方法，该方法测试初始化的字段。因为没有为该字段赋值，所以它的默认布尔值为 false。
*   同样，sum 的默认 int 值为 0。因此，initialize 方法实现了您所期望的，将 4，950 相加，并将 initialize 设置为 true。静态块执行后，初始化字段的静态初始化器将其设置回 false，完成 MyTest 的类初始化。不幸的是，sum 现在包含 4950，但初始化后包含 false。
*   The main method in the GFG class then invokes MyTest.getSum, which in turn invokes initialize method. Because the initialized flag is false, the initializeIf method enters its loop, which adds another 4, 950 to the value of sum, increasing its value to 9, 900\. The getSum method returns this value, and the program prints it

    本文由 [**舒巴姆·朱尼加**](https://auth.geeksforgeeks.org/profile.php?user=shubhamjuneja11) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。