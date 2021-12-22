# 理解 Java 中静态方法和静态变量的存储

> 原文:[https://www . geesforgeks . org/understand-storage-of-static-methods-and-static-variables-in-Java/](https://www.geeksforgeeks.org/understanding-storage-of-static-methods-and-static-variables-in-java/)

在每种编程语言中，内存都是一种至关重要的资源，本质上也是稀缺的。因此，彻底管理内存而不发生任何泄漏至关重要。[内存的分配和解除分配](https://www.geeksforgeeks.org/java-memory-management/)是一项关键任务，需要非常小心和考虑。在本文中，我们将了解 Java 中[静态方法](https://www.geeksforgeeks.org/static-methods-vs-instance-methods-java/)和[静态变量](https://www.geeksforgeeks.org/difference-between-static-and-non-static-variables-in-java/)的存储。

[Java 虚拟机(JVM)](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/) 是一个提供运行时环境来驱动 Java 代码的引擎。它将 java 字节码转换成机器语言。JVM 有两个主要功能。它们是:

1.  It allows java programs to run on any device or operating system to meet WORA principles.
2.  And manage the optimizer memory.

JVM 内存管理器在程序运行期间创建**内存池**。

让我们理解 java 中内存池的概念。内存池有两种类型，即[堆栈内存和堆内存](https://www.geeksforgeeks.org/stack-vs-heap-memory-allocation/)。堆栈内存和堆内存的主要区别在于，堆栈仅用于存储小数据类型，而堆存储类的所有实例。而且，由于 java 隐式或显式地扩展了 Object.class 的类，所以我们创建的每个类都是对象的集合。这也意味着我们不能使用一个方法或变量，除非我们用一个新的关键字实例化它。一旦我们实例化了这些方法，JVM 就会在堆上分配一些内存，并将实例的地址存储在堆栈上。之后，可以使用方法和变量。为了更好地理解新的关键词是如何产生的，让我们举个例子。让我们上一堂鸟类课。每当发现一只新的鸟，鸟的数量需要增加。

让我们试着实现这个代码:

```java
// Java program to demonstrate the above example

public class Bird {
    private String name;
    private int number;

    Bird(String name)
    {
        this.name = name;
        number++;
    }

    public void fly()
    {
        System.out.println(
            "This bird flies");
    }

    public int getNumber()
    {
        return number;
    }

    public String getName()
    {
        return name;
    }
}

class GFG {
    public static void main(String args[])
    {
        Bird b1 = new Bird("Parrot");
        Bird b2 = new Bird("Sparrow");
        Bird b3 = new Bird("Pigeon");

        System.out.println(b1.getNumber());
    }
}
```

**输出:**

```java
1

```

很明显，这个方法不能用来计算鸟的数量，因为在每个实例中，都会分配一个新的堆，并且对于所有实例，鸟的数量都是从 0 开始初始化，然后增加到 1。因此，我们正在创建三个独立的鸟，其中，在每个鸟对象中，鸟的数量是 1。为了避免这种情况，我们将方法和变量初始化为**静态**。这意味着每次创建新对象时，变量或方法都不会改变。由于这些方法和变量不能存储在一个正常的堆中，所以它们被存储在一个名为**永久生成(PermGen)** 的特殊区域中。

> 主要区别在于堆是自动增长的空间，以 RAM 内存为约束，而这个 PermGen 有固定的空间分配，这是所有实例共享的。

让我们通过将数字更改为静态变量来实现这一点。

```java
// Java program to demonstrate the above example

public class Bird {
    private String name;
    private static int number;

    Bird(String name)
    {
        this.name = name;
        number++;
    }

    public void fly()
    {
        System.out.println("This bird flies");
    }

    public int getNumber()
    {
        return number;
    }

    public String getName()
    {
        return name;
    }
}

class GFG {
    public static void main(String args[])
    {
        Bird b1 = new Bird("Parrot");
        Bird b2 = new Bird("Sparrow");
        Bird b3 = new Bird("Pigeon");

        System.out.println(b1.getNumber());
    }
}
```

**输出:**

```java
3

```

**注意:**在 Java 5 和 6 中，使用了 PermGen 空间。但是由于 Java 8 中内存模型的重大变化，存储规范也发生了变化。现在引入了一个新的内存空间“ **MetaSpace** ”，其中存储了类的所有名称字段、类的方法以及方法的字节码、常量池和 JIT 优化。Java 8.0 中 PermGen 发生这种变化的主要原因是很难预测 PermGen 的大小，这有助于提高垃圾收集性能。