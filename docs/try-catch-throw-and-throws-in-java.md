# Java 中的试、抓、投、掷

> 原文:[https://www . geesforgeks . org/try-catch-throw-and-throw-in-Java/](https://www.geeksforgeeks.org/try-catch-throw-and-throws-in-java/)

**什么是例外？**
[异常](https://www.geeksforgeeks.org/java-gq/exception-handling-2-gq/)是一种“不想要的或意外的事件”，它发生在程序执行期间，即运行时，会中断程序指令的正常流动。当异常发生时，程序的执行被终止。

**为什么会出现异常？**
由于网络连接问题、用户输入错误、打开程序中不存在的文件等原因，可能会出现异常

**阻止&用于异常处理的关键词**

1.**[try](https://www.geeksforgeeks.org/flow-control-in-try-catch-finally-in-java/)**:try 块包含一组可能发生异常的语句。

```
try
{
    // statement(s) that might cause exception
}

```

2. **catch** : Catch block 用于处理试块的不确定情况。try 块后面总是跟着 catch 块，catch 块处理关联 try 块中发生的异常。

```
catch
{
   // statement(s) that handle an exception
   // examples, closing a connection, closing
   // file, exiting the process after writing
   // details to a log file.
}

```

3.**投掷**:投掷关键字用于将控制从试块转移到接球块。

4.**抛出**:抛出关键字用于异常处理不用尝试&接球拦网。它指定了方法可以向调用方抛出的异常，并且不处理自身。

5.**最后**:抓块后执行。当有多个 catch 块时，我们基本上使用它来放置一些公共代码。

系统生成的异常示例如下:

```
Exception in thread "main" 
*java.lang.ArithmeticException*: divide 
by zero at *ExceptionDemo.main(ExceptionDemo.java:5)*
ExceptionDemo: The class name
main:The method name 
ExceptionDemo.java:The file name
java:5:line number

```

```
// Java program to demonstrate working of try,
// catch and finally

class Division {
    public static void main(String[] args)
    {
        int a = 10, b = 5, c = 5, result;
        try {
            result = a / (b - c);
            System.out.println("result" + result);
        }

        catch (ArithmeticException e) {
            System.out.println("Exception caught:Division by zero");
        }

        finally {
            System.out.println("I am in final block");
        }
    }
}
```

**Output:**

```
Exception caught:Division by zero
I am in final block

```

**一个例子[抛出](https://www.geeksforgeeks.org/throw-throws-java/)关键词:**

**T5】**

```
// Java program to demonstrate working of throws
class ThrowsExecp {

    // This method throws an exception
    // to be handled
    // by caller or caller
    // of caller and so on.
    static void fun() throws IllegalAccessException
    {
        System.out.println("Inside fun(). ");
        throw new IllegalAccessException("demo");
    }

    // This is a caller function 
    public static void main(String args[])
    {
        try {
            fun();
        }
        catch (IllegalAccessException e) {
            System.out.println("caught in main.");
        }
    }
}
```

**Output:**

```
Inside fun(). 
caught in main.

```