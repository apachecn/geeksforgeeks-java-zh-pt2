# Java 中的重载

> 原文:[https://www.geeksforgeeks.org/overloading-in-java/](https://www.geeksforgeeks.org/overloading-in-java/)

重载允许不同的方法具有相同的名称，但签名不同，其中签名可能因输入参数的数量或输入参数的类型或两者而异。重载与编译时(或静态)多态性有关。

```
// Java program to demonstrate working of method
// overloading in Java.

public class Sum {

    // Overloaded sum(). This sum takes two int parameters
    public int sum(int x, int y)
    {
        return (x + y);
    }

    // Overloaded sum(). This sum takes three int parameters
    public int sum(int x, int y, int z)
    {
        return (x + y + z);
    }

    // Overloaded sum(). This sum takes two double parameters
    public double sum(double x, double y)
    {
        return (x + y);
    }

    // Driver code
    public static void main(String args[])
    {
        Sum s = new Sum();
        System.out.println(s.sum(10, 20));
        System.out.println(s.sum(10, 20, 30));
        System.out.println(s.sum(10.5, 20.5));
    }
}
```

输出:

```
30
60
31.0

```

**问题出现:
Q .如果确切的原型与参数不匹配怎么办。**俺们 T3。
优先级方面，编译器采取以下步骤:

1.  类型转换，但在同一系列中转换为更高的类型(就范围而言)。
2.  类型转换到下一个更高的系列(假设如果没有长的数据类型可用于 int 数据类型，那么它将搜索 float 数据类型)。

让我们举个例子来澄清这个概念

```
class Demo {
    public void show(int x)
    {
        System.out.println("In int" + x);
    }
    public void show(String s)
    {
        System.out.println("In String" + s);
    }
    public void show(byte b)
    {
        System.out.println("In byte" + b);
    }
}
class UseDemo {
    public static void main(String[] args)
    {
        byte a = 25;
        Demo obj = new Demo();
        obj.show(a); // it will go to
        // byte argument
        obj.show("hello"); // String
        obj.show(250); // Int
        obj.show('A'); // Since char is
        // not available, so the datatype
        // higher than char in terms of
        // range is int.
        obj.show("A"); // String
        obj.show(7.5); // since float datatype
// is not available and so it's higher
// datatype, so at this step their
// will be an error.
}
}
```

**优势是什么？**
我们不必为做同样事情的函数创建和记住不同的名字。例如，在我们的代码中，如果 Java 不支持重载，我们将不得不创建像 sum1、sum2、…或 sum2Int、sum3Int、…等方法名。

**我们可以在返回类型上重载方法吗？**
我们**不能通过返回式**过载。这种行为在 C++中是相同的。详情请参考此处

```
public class Main {
    public int foo() { return 10; }

    // compiler error: foo() is already defined
    public char foo() { return 'a'; }

    public static void main(String args[])
    {
    }
}
```

但是，在显式指定被调用函数的数据类型的情况下，返回类型上的重载方法是可能的。请看下面的例子:

```
// Java program to demonstrate the working of method
// overloading in static methods
public class Main {

    public static int foo(int a) { return 10; }
    public static char foo(int a, int b) { return 'a'; }

    public static void main(String args[])
    {
        System.out.println(foo(1));
        System.out.println(foo(1, 2));
    }
}
```

输出:

```
10
a

```

```
// Java program to demonstrate working of method
// overloading in  methods
class A {
    public int foo(int a) { return 10; }

    public char foo(int a, int b) { return 'a'; }
}

public class Main {

    public static void main(String args[])
    {
        A a = new A();
        System.out.println(a.foo(1));
        System.out.println(a.foo(1, 2));
    }
}
```

输出:

```
10
a

```

**我们可以重载静态方法吗？**T2【答案是】**是的**。我们可以有两个或更多同名的静态方法，但是输入参数不同。例如，考虑下面的 Java 程序。详见[本](https://www.geeksforgeeks.org/can-we-overload-or-override-static-methods-in-java/)。

**我们可以重载仅通过静态关键字不同的方法吗？**
我们**不能**在 Java 中重载两个方法，如果它们只在静态关键字上不同(参数数量和参数类型相同)。参见下面的 Java 程序示例。详见[本](https://www.geeksforgeeks.org/can-we-overload-or-override-static-methods-in-java/)。

**我们可以在 Java 中重载 main()吗？**
像其他静态方法一样，我们**可以在 Java 中** [重载 main()。有关更多详细信息，请参考 Java 中的重载 main()。](https://www.geeksforgeeks.org/gfact-48-overloading-main-in-java/)

```
// A Java program with overloaded main()
import java.io.*;

public class Test {

    // Normal main()
    public static void main(String[] args)
    {
        System.out.println("Hi Geek (from main)");
        Test.main("Geek");
    }

    // Overloaded main methods
    public static void main(String arg1)
    {
        System.out.println("Hi, " + arg1);
        Test.main("Dear Geek", "My Geek");
    }
    public static void main(String arg1, String arg2)
    {
        System.out.println("Hi, " + arg1 + ", " + arg2);
    }
}
```

输出:

```
Hi Geek (from main)
Hi, Geek
Hi, Dear Geek, My Geek

```

【Java 支持运算符重载吗？
与 C++不同，Java 不允许用户定义的重载操作符。在内部，Java 重载操作符，例如,+被重载用于连接。

**超载和[超越](https://www.geeksforgeeks.org/overriding-in-java/)有什么区别？**

*   重载是指相同的函数有不同的签名。重写是关于相同的函数，相同的签名，但不同的类通过继承连接。
    [![OverridingVsOverloading](img/1ce4f1c55d752918296c29291c3ef292.png)](http://media.geeksforgeeks.org/wp-content/uploads/OverridingVsOverloading.png)
*   重载是编译器时间多态性的一个例子，重写是运行时多态性的一个例子。

**相关文章:**

*   [Java 中方法重载的不同方式](https://www.geeksforgeeks.org/different-ways-method-overloading-java/)
*   [Java 中方法重载和空错误](https://www.geeksforgeeks.org/method-overloading-null-error-java/)
*   [我们可以重载或者覆盖 java 中的静态方法吗？](https://www.geeksforgeeks.org/can-we-overload-or-override-static-methods-in-java/)

本文由 **Shubham Agrawal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。