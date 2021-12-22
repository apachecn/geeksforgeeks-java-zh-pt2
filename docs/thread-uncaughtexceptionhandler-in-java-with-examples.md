# Java 中线程未跳脱异常处理器，示例

> 原文:[https://www . geeksforgeeks . org/thread-uncashicalexceptionhandler-in-Java-with-examples/](https://www.geeksforgeeks.org/thread-uncaughtexceptionhandler-in-java-with-examples/)

[异常](https://www.geeksforgeeks.org/java-gq/exception-handling-2-gq/)是在程序执行过程中，即在运行时发生的不希望的或意外的事件，它会中断程序指令的正常流动。

在本文中，我们将了解如何实现**线程。打开异常处理器**。

在实现处理程序之前，让我们了解异常是如何由如下示例引起的:

```
public class GFG {

    public static void main(String args[])
    {
        System.out.println(10 / 0);
    }
}
```

上述代码的输出是

```
Exception in thread "main"
 java.lang.ArithmeticException:
 / by zero at Demo.main(GFG.java:5)

```

但是，如果我们希望覆盖 JVM 的[内部工作，以便在发生异常时显示自定义消息，我们可以使用线程。取消处理异常句柄。](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/)

**[java.lang.Thread](https://www.geeksforgeeks.org/java-lang-thread-class-java/)** 类的**setDefaultUncutexceptionHandler()**方法用于覆盖 JVM 处理未捕获异常的方式。

**语法:**

> public static void setdefaultunchechtxceptionhandler(unchechtxceptionhandler eh)

**参数:**该方法以类型为*的对象*为参数。

下面是说明 setdefaultuncutexceptionhandler()方法的示例:

**示例 1:** 让我们尝试创建一个类，该类实现来自线程类的接口 UncaughtExceptionHandler 来处理除以 0 的异常，如下所示:

```
// Java program to demonstrate
// the exception handler

// Creating a random class to
// implement the interface
class Random
    implements Thread
                   .UncaughtExceptionHandler {

    // Method to handle the
    // uncaught exception
    public void uncaughtException(
        Thread t, Throwable e)
    {

        // Custom task that needs to be
        // performed when an exception occurs
        System.out.println(
            "Welcome to GeeksforGeeks");
    }
}

public class GFG {

    public static void main(String[] args)
    {

        // Passing the object of the type
        // UncaughtExceptionHandler to the
        // setter method
        // setDefaultUncaughtExceptionHandler()
        Thread
            .setDefaultUncaughtExceptionHandler(
                new Random());

        System.out.println(10 / 0);
    }
}
```

**输出:**

> 欢迎来到极客博客

**注意:**上面的代码在联机 IDE 上不起作用，因为联机 IDE 没有给出覆盖异常处理程序的权限。在这里，**设置默认值异常处理程序()**方法，将字段*从初始值 null 更改为随机类。当未捕获的异常发生时，调用了*随机*类的**未捕获异常()**方法。*

**示例 2:** 在这个示例中，让我们抛出一个新的异常，并了解如何处理异常。

```
// Java program to demonstrate
// the exception handler

// Creating a random class to
// implement the interface
class Random
    implements Thread.UncaughtExceptionHandler {

    // Method to handle the
    // uncaught exception
    public void uncaughtException(
        Thread t, Throwable e)
    {

        // Custom task that needs to be
        // performed when an exception occurs
        System.out.println(
            "Exception Handled " + e);
    }
}

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // Passing the object of the type
        // UncaughtExceptionHandler to the
        // setter method
        // setDefaultUncaughtExceptionHandler()
        Thread.setDefaultUncaughtExceptionHandler(
            new Random());

        throw new Exception("Exception");
    }
}
```

**输出:**

> 异常处理异常