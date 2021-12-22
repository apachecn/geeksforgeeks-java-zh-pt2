# 超和 Java 中的这个关键词

> 原文:[https://www . geesforgeks . org/super-and-this-keywords-in-Java/](https://www.geeksforgeeks.org/super-and-this-keywords-in-java/)

super 关键字用于访问**父类**的方法，而这用于访问**当前类**的方法。

[**这个关键词**](https://www.geeksforgeeks.org/this-reference-in-java/)

1.  **这个**是 java 中的一个保留关键字，也就是我们不能用它作为标识符。
2.  **这个**用来指代**当前类的实例以及静态成员。**

**该**可用于如下给出的各种上下文:

*   引用当前类的实例变量
*   调用或启动当前类构造函数
*   可以在方法调用中作为参数传递
*   可以在构造函数调用中作为参数传递
*   可用于返回当前类实例

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Program to illustrate this keyword
// is used to refer current class
class RR {
    // instance variable
    int a = 10;

    // static variable
    static int b = 20;

    void GFG()
    {
        // referring current class(i.e, class RR)
        // instance variable(i.e, a)
        this.a = 100;

        System.out.println(a);

        // referring current class(i.e, class RR)
        // static variable(i.e, b)
        this.b = 600;

        System.out.println(b);
    }

    public static void main(String[] args)
    {
        // Uncomment this and see here you get
        // Compile Time Error since cannot use
        // 'this' in static context.
        // this.a = 700;
        new RR().GFG();
    }
}
```

```
100
600

```

[**超**](https://www.geeksforgeeks.org/super-keyword/) **关键词**

1.  **super** 是 java 中的一个保留关键字，也就是我们不能用它作为标识符。
2.  **super** 用于指代**超类的实例以及静态成员**。
3.  **super** 也用于调用**超类的方法或构造函数**。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Program to illustrate super keyword
// refers super-class instance

class Parent {
    // instance variable
    int a = 10;

    // static variable
    static int b = 20;
}

class Base extends Parent {
    void rr()
    {
        // referring parent class(i.e, class Parent)
        // instance variable(i.e, a)
        System.out.println(super.a);

        // referring parent class(i.e, class Parent)
        // static variable(i.e, b)
        System.out.println(super.b);
    }

    public static void main(String[] args)
    {
        // Uncomment this and see here you get
        // Compile Time Error since cannot use 'super'
        // in static context.
        // super.a = 700;
        new Base().rr();
    }
}
```

```
10
20

```

**这和超级**的相似之处

1)除了静态区域外，我们可以在任何地方使用*这个*以及*超级*T4。上面已经展示了这个例子，我们在公共静态 void main(String[]args)中使用了这个和 super，因此我们得到了编译时错误，因为不能在静态区域中使用它们。
2)我们可以在一个程序中任意多次使用*这个*以及*超级* **。** 

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate using this
// many number of times

class RRR {
    // instance variable
    int a = 10;

    // static variable
    static int b = 20;

    void GFG()
    {
        // referring current class(i.e, class RR)
        // instance variable(i.e, a)
        this.a = 100;

        System.out.println(a);

        // referring current class(i.e, class RR)
        // static variable(i.e, b)
        this.b = 600;

        System.out.println(b);

        // referring current class(i.e, class RR)
        // instance variable(i.e, a) again
        this.a = 9000;

        System.out.println(a);
    }

    public static void main(String[] args)
    {
        new RRR().GFG();
    }
}
```

```
100
600
9000

```

看上面我们已经用了**这个** 3 次了。所以**这个**可以任意多次使用。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate using super
// many number of times

class Parent {
    // instance variable
    int a = 36;

    // static variable
    static float x = 12.2f;
}

class Base extends Parent {
    void GFG()
    {
        // referring super class(i.e, class Parent)
        // instance variable(i.e, a)
        super.a = 1;
        System.out.println(a);

        // referring super class(i.e, class Parent)
        // static variable(i.e, x)
        super.x = 60.3f;

        System.out.println(x);
    }
    public static void main(String[] args)
    {
        new Base().GFG();
    }
}
```

```
1
60.3

```

看上面我们已经用了**超** 2 次了。所以**超级**可以任意多次使用。
**注:**我们可以任意多次使用‘this’和‘super’，但主要是我们**不能**在静态上下文中使用它们。
让我们考虑一个**棘手的**这个关键词的例子:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// the usage of this keyword

class RR {
    int first = 22;
    int second = 33;

    void garcia(int a, int b)
    {
        a = this.first;
        b = this.second;
        System.out.println(first);
        System.out.println(second);
        System.out.println(a);
        System.out.println(b);
    }

    void louis(int m, int n)
    {
        this.first = m;
        this.second = n;
        System.out.println(first);
        System.out.println(second);
        System.out.println(m);
        System.out.println(n);
    }

    public static void main(String[] args)
    {
        new RR().garcia(100, 200);
        new RR().louis(1, 2);
    }
}
```

```
//it is of S.O.P(first) of garcia method
22
//it is of S.O.P(second) of garcia method
33
//it is of S.O.P(a) of garcia method
22
//it is of S.O.P(b) of garcia method
33
//it is of S.O.P(first) of louis method
1
//it is of S.O.P(second) of louis method
2
//it is of S.O.P(m) of louis method
1
//it is of S.O.P(n) of louis method
2

```

**程序流程:**首先从 main 开始，然后我们有**新 RR()。加西亚(100，200)** 然后流程转到 RR 类的加西亚方法，然后我们有

```
a = this.first
b = this.second 

```

这里，正在发生的是实例变量(即第一个)的值和静态变量(即第二个)的值分别分配给 garcia 方法的局部变量 a 和 b。因此 a 和 b 的值分别是 22 和 33。接下来我们有**新 RR()。路易斯(1，2)** 因此这里的流程转到 RR 类的路易斯方法，因为我们有

```
this.first = m
this.second = n

```

这里，上面发生的是，路易方法的局部变量，即 m 和 n 的值被分配给实例以及静态变量，即第一个和第二个。
因此，第一个和第二个变量的值是相同的，我们已经传递到路易方法，即 1 和 2。

**我们可以在同一个构造函数中同时使用 this()和 super()吗？**

这里需要注意的一个有趣的事情是，根据 Java 准则，这个()或 super()必须是构造函数块中的第一条语句才能执行。因此，我们不能将它们放在同一个构造函数中，因为它们都需要是块中的第一条语句才能正确执行，这是不可能的。尝试这样做会引发编译器错误。

## Java 语言(一种计算机语言，尤用于创建网站)

```
class Vehicle {
    Vehicle() { System.out.println("Vehicle is created."); }
}

class Bike extends Vehicle {
    Bike() { System.out.println("Bike is created."); }

    Bike(String brand)
    {
        super(); // it calls Vehicle(), the parent class
                 // constructor of class Bike
        this();
        System.out.println("Bike brand is " + brand);
    }
}

public class GFG {
    public static void main(String args[])
    {
        Bike bike = new Bike("Honda");
    }
}
```

在运行上述程序时，我们在第 12 行得到一个错误，说“对此的调用必须是构造函数中的第一个语句”。这是因为我们尝试同时使用 super()和 This()。虽然 super()是构造函数的第一行，但是这个()语句违反了它应该是第一行的条件，因此引发了一个错误。

**编译错误:**

```
prog.java:12: error: call to this must be first statement in constructor
        this();
            ^
1 error
```

本文由 **Rajat Rawat** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。