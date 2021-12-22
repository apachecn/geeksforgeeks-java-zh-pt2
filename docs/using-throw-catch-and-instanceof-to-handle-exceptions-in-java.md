# 使用抛出、捕获和实例来处理 Java 中的异常

> 原文:[https://www . geeksforgeeks . org/使用-throw-catch-instance of-to-handle-exceptions-in-Java/](https://www.geeksforgeeks.org/using-throw-catch-and-instanceof-to-handle-exceptions-in-java/)

**先决条件:**[Java 中的 Try-Catch Block](https://www.geeksforgeeks.org/flow-control-in-try-catch-finally-in-java/)
在 Java 中，您的程序可能会遇到异常，为此语言提供了 Try-Catch 语句来处理它们。但是，包含在“try”块中的代码可能容易受到多个异常的影响。例如，看看下面的示例代码:

```
// A sample Java code with a try catch block
// where the try block has only one catch block
// to handle all possible exceptions

// importing class Random to generate a random number as input
import java.util.Random;
class A {
    void func(int n)
    {
        try {

            // this will throw ArithmeticException if n is 0
            int x = 10 / n;
            int y[] = new int[n];

            // this will throw ArrayIndexOutOfBoundsException
            // if the value of x surpasses
            // the highest index of this array
            y[x] = 10;
        }
        catch (Exception e) {
            System.out.println("Exception occurred");
        }
    }
    public static void main(String a[])
    {
        new A().func(new Random().nextInt(10));
    }
}
```

**任何一种异常情况下的输出**:

```
Exception occurred
```

从上面的代码中可以看出，上面提到的两种异常都有可能发生。为了处理这两者，catch 语句通过传递对异常类的引用来接受任何可能发生的异常，异常类是所有异常类的父类。然而，这个 catch 语句对所有类型的异常都做同样的事情。

**为不同的异常指定自定义操作**

为了在这种情况下指定自定义操作，程序员通常会放入多个 catch 语句，如下例所示:

```
// A sample Java code with one try block
// having multiple catch blocks to catch
// different exceptions

// importing class Random to generate a random number as input
import java.util.Random;
class A {
    void func(int n)
    {
        try {

            // this will throw ArithmeticException if n is 0
            int x = 10 / n;
            int y[] = new int[n];

            // this will throw ArrayIndexOutOfBoundsException
            // if the value of x surpasses
            // the highest index of this array
            y[x] = 10;
        }
        catch (ArithmeticException e) {
            System.out.println("Dividing by 0");
        }
        catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("That index doesn't exist");
        }
    }
    public static void main(String a[])
    {
        new A().func(new Random().nextInt(10));
    }
}
```

**输出**:

```
a) In case of ArithmeticException: Dividing by 0
b) In case of ArrayIndexOutOfBoundsException: That index doesn't exist
```

**使用**的实例为不同的异常指定自定义操作

但是，有一种方法可以做到同样的事情，只使用**一个抓块**。为此，java 提供了一个运算符:的实例。
通过使用这个操作符，我们可以为发生的不同异常指定自定义操作。以下程序演示了如何:

```
// Java program to demonstrate the use of
// instanceof to specify different actions for
// different exceptions using only one catch block

// importing class Random to generate a random number as input
import java.util.Random;
class A {
    void func(int n)
    {
        try {

            // this will throw ArithmeticException if n is 0
            int x = 10 / n;
            int y[] = new int[n];
            y[x] = 10;

            // this will throw ArrayIndexOutOfBoundsException
            // if the value of x surpasses
            // the highest index of this array
            System.out.println("No exception arose");
        }
        catch (Exception e) {
            if (e instanceof ArithmeticException)
                System.out.println("Can't divide by 0");
            if (e instanceof ArrayIndexOutOfBoundsException)
                System.out.println("This index doesn't exist in this array");
        }
    }
    public static void main(String a[])
    {
        new A().func(new Random().nextInt(10));
    }
}
```

**输出:**

```
a) In case of ArithmeticException: 
Can't divide by 0
b) In case of ArrayIndexOutOfBoundsException: 
This index doesn't exist in this array
c) In case of no exception: No exception arose
```

通过在异常处理中使用运算符的**实例，很容易实现上述目标，同时也使您的代码不那么复杂。这里需要注意的一点是，一旦 try 块遇到异常，控件将直接跳转到 catch 块进行处理，从而阻止 try 块的其余部分执行。因此，**即使可能出现多个异常，在将控制转移到 catch 块之前，try 块也只会抛出一个异常。****