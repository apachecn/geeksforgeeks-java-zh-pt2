# c++和 Java 中静态关键字的比较

> 原文:[https://www.geeksforgeeks.org/static-keyword-in-java/](https://www.geeksforgeeks.org/static-keyword-in-java/)

在 C++和 Java 中，Static 关键字的用途几乎相同。尽管有一些不同。这篇文章涵盖了 C++和 Java 中静态关键字的异同。

**静态关键字 C++和 Java 的相似之处:**

*   静态数据成员可以用两种语言定义。
*   静态成员函数可以用两种语言定义。
*   静态成员的简单访问是可能的，不需要创建一些对象。

**c++与 Java 的区别对于静态关键字:**

<figure class="table">

| 

c++

 | 

Java

 |
| --- | --- |
| C++ does not support static blocks. | Java supports static blocks (also called static clauses). It is used for static initialization of classes. |
| Static local variables can be declared. | Static local variables are not supported. |

</figure>

***以上几点讨论如下:***

**1。静态数据成员:**和 C++一样，Java 中的静态数据成员是类成员，在所有对象之间共享。例如，在下面的 Java 程序中，静态变量 *count* 用于计算创建的对象数量。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
class Test {
    static int count = 0;

    Test() { count++; }
    public static void main(String arr[])
    {
        Test t1 = new Test();
        Test t2 = new Test();
        System.out.println("Total " + count
                           + " objects created");
    }
}
```

**Output**

```java
Total 2 objects created
```

**2。静态成员方法:**在 C++和 Java 中，可以定义静态成员函数。声明为静态的方法是类成员，并且有以下限制:

**A)** 他们只能调用其他静态方法。例如，以下程序在编译中失败。fun()是非静态的，它在静态 main()中被调用。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
class Main {
    public static void main(String args[])
    {
        System.out.println(fun());
    }
    int fun() { return 20; }
}
```

**B)** 他们必须只访问静态数据。

**C)** 他们无法访问 [*这个*](https://www.geeksforgeeks.org/this-pointer-in-c/) [](http://docs.oracle.com/javase/tutorial/java/javaOO/thiskey.html)或者 [*超级*](https://www.geeksforgeeks.org/super-keyword/) 。例如，以下程序在编译中失败。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
class Base {
    static int x = 0;
}

class Derived extends Base {
    public static void fun()
    {

        // Compiler Error: non-static variable
        // cannot be referenced from a static context
        System.out.println(super.x);
    }
}
```

**D)** 像 C++一样，静态数据成员和静态方法可以在不创建对象的情况下访问。可以使用类名访问它们。例如，在下面的程序中，静态数据成员计数和静态方法 fun()是在没有任何对象的情况下访问的。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
class Test {
    static int count = 0;
    public static void fun()
    {
        System.out.println("Static fun() called");
    }
}

class Main {
    public static void main(String arr[])
    {
        System.out.println("Test.count = " + Test.count);
        Test.fun();
    }
}
```

**Output**

```java
Test.count = 0
Static fun() called
```

**3。静态块:**与 C++不同，Java 支持一种特殊的块，称为静态块(也称为 Static 子句)，可用于类的静态初始化。静态块中的这段代码只执行一次。详见 Java 中的[静态块。](https://www.geeksforgeeks.org/g-fact-79/)

**4。静态局部变量:**与 Java 不同，C++支持静态局部变量。例如，下面的 Java 程序在编译中失败。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
class Test {
    public static void main(String args[])
    {
        System.out.println(fun());
    }
    static int fun()
    {

        // Compiler Error: Static local
        // variables are not allowed
        static int x = 10;
        return x--;
    }
}
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。