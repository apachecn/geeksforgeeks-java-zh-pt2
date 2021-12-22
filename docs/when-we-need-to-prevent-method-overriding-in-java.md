# 什么时候我们需要防止 Java 中的方法重写？

> 原文:[https://www . geeksforgeeks . org/当我们需要在 java 中防止方法重写时/](https://www.geeksforgeeks.org/when-we-need-to-prevent-method-overriding-in-java/)

这里我们将讨论为什么我们应该防止 java 中的方法重写。因此，在进入主题之前，让我们先看一下下面的重要概念，然后我们将进入实际的主题。正如我们所知[面向对象编程(OOPs)](https://www.geeksforgeeks.org/object-oriented-programming-oops-concept-in-java/) 概念由以下 4 个重要概念组成:

1.  [封装](https://www.geeksforgeeks.org/encapsulation-in-java/)
2.  [继承](https://www.geeksforgeeks.org/inheritance-in-java/)
3.  [多态性](https://www.geeksforgeeks.org/polymorphism-in-java/)
4.  [抽象](https://www.geeksforgeeks.org/abstraction-in-java-2/)

多态性是 Oops 的 4 个支柱中的重要支柱 **s** 之一，指的是以不同的方式执行单个动作。这意味着对象在不同的条件下表现不同。它分为两大类，即

1.  编译时多态性或静态多态性或早期绑定。
    *   示例:[方法重载](https://www.geeksforgeeks.org/overloading-in-java/)
2.  运行时多态性或动态多态性或后期绑定。
    *   示例:[方法覆盖](https://www.geeksforgeeks.org/overriding-in-java/)

[方法重载和](https://www.geeksforgeeks.org/difference-between-method-overloading-and-method-overriding-in-java/)方法覆盖也有一些不同。当在一个项目中实际工作时，会出现一些情况，当我们需要实现重载或重写时，以及在一些场景中，我们需要防止重载和重写。因为我们的主题旨在关注“为什么我们要阻止方法重写？”让我们进入那个部分。在任何项目中工作时，我们[以不同的方式避免方法覆盖](https://www.geeksforgeeks.org/different-ways-to-prevent-method-overriding-in-java/)，主要有以下两个原因:

1.  性能参数
2.  设计方案

让我们通过深入讨论来讨论和实施它们。

**原因 1:** 性能参数

在重写时，JVM 会在运行时执行额外的工作，这会影响性能。是的，它是方法绑定，这意味着将被调用的方法是在运行时根据引用所指向的实际对象来决定的，所以它需要额外的时间，而在编译时的静态绑定中，将被调用的方法是决定的(函数调用与适当的方法绑定)。因此，很明显，我们在防止覆盖意味着我们在防止运行时绑定，我们在防止运行时绑定意味着我们在节省时间和提高性能。因此，有时我们会阻止重写来提高软件应用程序的性能。

**原因 2:** 设计决策

在许多情况下，我们不希望通过特定基类方法的派生类来改变它们的行为。这意味着我们希望保持父类方法不变，不被它的子类改变。

**实施:**

我们有一个基本类汽车和一个衍生类斯柯达汽车，其中基本类有以下 3 种方法:

*   速度()
*   条件()
*   维护()

这里我们希望 speed()方法保持原样，另外两个方法 condition()方法和 maintenance()方法被更改(表示在派生类中提供的 body)。如下例所述。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustatte Prevention method overriding

// Importing input output classes
import java.io.*;

// Class 1
// Base class
class Car {

    // We do not want spped to be changed change in base
    // class, so we will not provide any body to speed()
    // method in derived class So we will provide new body
    // to condition() method and maintenance() method in
    // derived class

    // Methods of this class
    public final void speed()
    {

        // Print statement
        System.out.println("Maximum speed allowed");
    }
    public void condition()
    {
        // Print statement
        System.out.println("good");
    }
    public void maintenance()
    {
        // Print statement
        System.out.println("required");
    }
}

// Class 2
// Derived class
class Skoda_Car extends Car {
    public void condition()
    {

        // Print statement
        System.out.println("Car condition good");
    }

    public void maintenance()
    {

        // Print statement
        System.out.println("Maintenance not required");
    }
}

// Class 3
// Main class
class Main {

    // Main drive method
    public static void main(String[] args)
    {

        // Here Parent class reference refers to
        // a Child object so child class methods will be
        // called This is known as run -time polymorphism

        // Creating an object of child class in Main class
        Skoda_Car c = new Skoda_Car();

        // Calling methods in Base class over object created
        // above
        c.speed();
        c.condition();
        c.maintenance();
    }
}
```

**Output**

```
Maximum speed allowed
Car condition good
Maintenance not required

```