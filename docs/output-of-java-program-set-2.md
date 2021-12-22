# Java 程序输出|第二集

> 原文:[https://www.geeksforgeeks.org/output-of-java-program-set-2/](https://www.geeksforgeeks.org/output-of-java-program-set-2/)

预测以下 Java 程序的输出。

**问题 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
package main;

class Base {
    public void Print()
    {
        System.out.println("Base");
    }
}

class Derived extends Base {
    public void Print()
    {
        System.out.println("Derived");
    }
}

class Main {
    public static void DoPrint(Base o)
    {
        o.Print();
    }
    public static void main(String[] args)
    {
        Base x = new Base();
        Base y = new Derived();
        Derived z = new Derived();
        DoPrint(x);
        DoPrint(y);
        DoPrint(z);
    }
}
```

**输出:**

```java
Base
Derived
Derived
```

预测第一行输出很容易。我们创建一个 Base 类型的对象，并调用 DoPrint()。DoPrint 调用 Print 函数，我们得到第一行。

DoPrint(y)导致第二行输出。像 C++一样，在 Java 中允许将派生类引用分配给基类引用。因此，表达式 Base y = new Derived()在 Java 中是有效的语句。在 DoPrint()中，o 开始引用与 y 引用的对象相同的对象。此外，与 C++不同，函数在 Java 中默认是虚拟的。因此，当我们调用 o.print()时，派生类的 print()方法被调用，这是由于 Java 中默认存在运行时多态性。

DoPrint(z)导致第三行输出，我们传递一个派生类的引用，再次调用派生类的 Print()方法。这里需要注意的一点是:与 C++不同，[对象切片](http://en.wikipedia.org/wiki/Object_slicing)在 Java 中不会发生。因为非基元类型总是通过引用赋值的。

**问题 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
package main;

// filename Main.java
class Point {
    protected int x, y;

    public Point(int _x, int _y)
    {
        x = _x;
        y = _y;
    }
}

public class Main {
    public static void main(String args[])
    {
        Point p = new Point();
        System.out.println("x = " + p.x + ", y = " + p.y);
    }
}
```

**输出:**

```java
Compiler Error
```

在上面的程序中，没有访问权限问题，因为点和主在同一个包中，并且一个类的受保护成员可以在同一个包的其他类中访问。代码的问题是:*Point 中没有默认构造函数。*

[像 C++](https://www.geeksforgeeks.org/does-c-compiler-create-default-constructor-when-we-write-our-own/) 一样，如果我们自己编写参数化的构造函数，那么 Java 编译器不会创建默认的构造函数。所以对 Point 类有以下两个修改可以修复上面的程序。

1.  移除参数化构造函数。
2.  添加不带任何参数的构造函数。

Java 不支持默认参数，所以这不是一个选项。
如果您发现任何答案/解释不正确，或者想分享更多关于上述讨论主题的信息，请写评论。