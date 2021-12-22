# Java 中的扔和掷

> 原文:[https://www.geeksforgeeks.org/throw-throws-java/](https://www.geeksforgeeks.org/throw-throws-java/)

**投**

Java 中的 throw 关键字用于从方法或任何代码块中显式抛出异常。我们可以抛出[选中或未选中的异常](https://www.geeksforgeeks.org/checked-vs-unchecked-exceptions-in-java/)。throw 关键字主要用于抛出自定义异常。

**语法:**

```java
throw ***Instance***
Example:
throw new ArithmeticException("/ by zero");
```

但是这个例外，即*实例*必须是类型**可投掷**或者是**可投掷**的子类。例如，异常是可抛出的子类，[用户定义的异常通常扩展异常类](https://www.geeksforgeeks.org/g-fact-32-user-defined-custom-exception-in-java/)。与 C++不同，诸如 int、char、floats 或不可抛出类等数据类型不能用作异常。

在抛出语句执行后，程序的执行流程立即停止，并检查最近的封闭 **try** 块，看它是否有与异常类型匹配的 **catch** 语句。如果发现匹配，控制转移到该语句，否则下一个封闭的**尝试**块被检查，以此类推。如果没有找到匹配的 **catch** ，那么默认异常处理程序将暂停程序。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program that demonstrates the use of throw
class ThrowExcep
{
    static void fun()
    {
        try
        {
            throw new NullPointerException("demo");
        }
        catch(NullPointerException e)
        {
            System.out.println("Caught inside fun().");
            throw e; // rethrowing the exception
        }
    }

    public static void main(String args[])
    {
        try
        {
            fun();
        }
        catch(NullPointerException e)
        {
            System.out.println("Caught in main.");
        }
    }
}
```

**输出:**

```java
Caught inside fun().
Caught in main.
```

**另一个例子:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program that demonstrates the use of throw
class Test
{
    public static void main(String[] args)
    {
        System.out.println(1/0);
    }
}
```

**输出:**

```java
Exception in thread "main" java.lang.ArithmeticException: / by zero
```

**投掷**

throws 是 Java 中的一个关键字，用在方法的签名中，表示这个方法可能会抛出一个列出的类型异常。这些方法的调用方必须使用 try-catch 块来处理异常。

**语法:**

```java
type method_name(parameters) throws exception_list
exception_list is a comma separated list of all the 
exceptions which a method might throw.
```

在程序中，如果有机会引发异常，那么编译器总是会警告我们，并强制我们处理该检查过的异常，否则我们会得到编译时错误，说**未报告的异常 XXX 必须被捕获或声明为抛出**。为了防止这种编译时错误，我们可以用两种方式处理异常:

1.  使用[试着抓住](https://www.geeksforgeeks.org/flow-control-in-try-catch-finally-in-java/)
2.  通过使用**抛出**关键字

我们可以使用 throws 关键字将异常处理的责任委托给调用者(它可能是一个方法或 JVM)，然后调用者方法负责处理该异常。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate error in case
// of unhandled exception
class tst
{
    public static void main(String[] args)
    {
        Thread.sleep(10000);
        System.out.println("Hello Geeks");
    }
}
```

**输出:**

```java
error: unreported exception InterruptedException; must be caught or declared to be thrown
```

**说明:**在上面的程序中，我们得到的是编译时错误，因为如果主线程要休眠，就有可能出现异常，其他线程得到的是执行 main()方法的机会，这会导致 InterruptedException。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate throws
class tst
{
    public static void main(String[] args)throws InterruptedException
    {
        Thread.sleep(10000);
        System.out.println("Hello Geeks");
    }
}
```

**输出:**

```java
Hello Geeks
```

**解释:**在上面的程序中，通过使用 throws 关键字，我们处理了中断异常，我们将获得输出为**你好极客**

**另一个例子:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of throws
class ThrowsExecp
{
    static void fun() throws IllegalAccessException
    {
        System.out.println("Inside fun(). ");
        throw new IllegalAccessException("demo");
    }
    public static void main(String args[])
    {
        try
        {
            fun();
        }
        catch(IllegalAccessException e)
        {
            System.out.println("caught in main.");
        }
    }
}
```

**输出:**

```java
Inside fun().
caught in main.
```

**关于投掷要记住的要点关键词:**

*   只有选中的异常才需要 throws 关键字，对于未选中的异常使用 throws 关键字是没有意义的。
*   只有说服编译器才需要抛出关键字，使用抛出关键字并不能防止程序的异常终止。
*   借助 throws 关键字，我们可以向方法的调用方提供关于异常的信息。

**参考文献:**Java——赫伯特·席尔德的完整参考文献

本文由 [**普拉蒂克·阿加瓦尔**](https://www.facebook.com/Pratik.Agarwal01) **和比沙尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。