# Java 中的多态性

> 原文:[https://www.geeksforgeeks.org/polymorphism-in-java/](https://www.geeksforgeeks.org/polymorphism-in-java/)

多态这个词意味着有许多形式。简单地说，我们可以将多态性定义为一条消息以多种形式显示的能力。

**实景图:**多态性

一个人同时可以有不同的特点。喜欢一个男人的同时是一个父亲，一个丈夫，一个员工。所以同一个人在不同的情况下有不同的行为。这叫做多态性。
多态性被认为是面向对象编程的重要特征之一。多态性允许我们以不同的方式执行单个动作。换句话说，多态性允许您定义一个接口并拥有多个实现。“聚”这个词的意思是多，“形”的意思是形式，所以它的意思是多种形式。

**多态性类型**

在 Java 中多态性主要分为两种类型:

*   编译时多态性
*   运行时多态性

**类型 1:** 编译时多态性

它也被称为静态多态性。这种类型的多态性是通过函数重载或运算符重载实现的。

> **注意:**但是 Java 不支持运算符重载。

![](img/1ce4f1c55d752918296c29291c3ef292.png)

**方法重载**:当存在多个同名但参数不同的函数时，则称这些函数为**重载**。参数数量的变化或/和参数类型的变化会导致函数过载。

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program for Method overloading
// By using Different Types of Arguments 

// Class 1
// Helper class
class Helper {

    // Method with 2 integer parameters
    static int Multiply(int a, int b)
    {

        // Returns product of integer numbers
        return a * b;
    }

    // Method 2
    // With same name but with 2 double parameters
    static double Multiply(double a, double b)
    {

        // Returns product of double numbers
        return a * b;
    }
}

// Class 2
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Calling method by passing
        // input as in arguments
        System.out.println(Helper.Multiply(2, 4));
        System.out.println(Helper.Multiply(5.5, 6.3));
    }
}
```

**Output:** 

```java
8
34.65
```