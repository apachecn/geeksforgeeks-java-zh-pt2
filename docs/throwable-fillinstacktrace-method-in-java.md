# Java 中的 Throwable fillInStackTrace()方法

> 原文:[https://www . geeksforgeeks . org/throwable-fillistancktrace-method-in-Java/](https://www.geeksforgeeks.org/throwable-fillinstacktrace-method-in-java/)

**java.lang.Throwable** 类的**fillistancktrace()**方法在这个 Throwable 对象中记录当前线程堆栈帧的当前状态信息。这意味着使用此方法可以看到类的当前方法的异常消息，其中调用了 fillInStackTrace()方法。如果有其他消息可以从当前方法中派生出来，并引发异常，那么可以跳过这些额外的消息细节。

**语法:**

```java
public Throwable fillInStackTrace()
```

**返回值:**这个方法返回一个对这个可抛出对象的引用，fillInStackTrace()应用于这个对象。

下面的程序说明了方法类的 fillInStackTrace()方法:

**程序 1:** 该程序显示如果不使用 filinstacktrace()方法会打印什么结果，如果使用 filinstacktrace()方法会发生什么情况

*说明:*使用 fillInStackTrace()只返回当前线程的帧活动状态信息。因此，当调用 filinstacktrace()时，该方法将返回调用 filinstacktrace()方法的主方法的详细信息。

```java
// Java program to demonstrate
// fillInStackTrace() method

public class GFG {
    // Main Method
    public static void main(String[] args) throws Throwable
    {
        GFG gfg = new GFG();
        try {
            // calling this method will throw exception
            gfg.method();
        }
        catch (Exception e) {

            // Exception details without using fillInStackTrace()

            System.out.println("Exception details without fillInStackTrace()\n");
            System.err.println("Caught Inside Main:");
            e.printStackTrace();

            // Exception details using fillInStackTrace()

            System.out.println("Exception details with fillInStackTrace()\n");
            System.err.println("Caught Inside Main:");
            e.fillInStackTrace();
            e.printStackTrace();
        }
    }

    // method calling divide operation
    public void method() throws Throwable
    {
        divide();
    }

    // divide operation throws ArithmeticException exception
    void divide()
    {

        try {
            System.out.println(10 / 0);
        }
        catch (ArithmeticException e) {
            throw e;
        }
    }
}
```

**输出:**

```java
Exception details without fillInStackTrace()

Caught Inside Main:
java.lang.ArithmeticException: / by zero
    at GFG.divide(GFG.java:38)
    at GFG.method(GFG.java:31)
    at GFG.main(GFG.java:13)

Exception details with fillInStackTrace()

Caught Inside Main:
java.lang.ArithmeticException: / by zero
    at GFG.main(GFG.java:23)

```

**程序 2:** 应用 fillInStackTrace()后，该程序打印详细信息。

*说明:*使用 fillInStackTrace()只返回当前线程的帧活动状态信息。因此，当调用 filinstacktrace()时，该方法将返回异常详细信息，直到调用 filinstacktrace()方法的 showResults 方法。但是 main()方法显示了整个异常细节，因为在 main 方法中没有调用 fillInStackTrace()。

```java
// Java program to demonstrate
// fillInStackTrace() method

public class GFG {

    // Main Method
    public static void main(String[] args) throws Throwable
    {
        GFG gfg = new GFG();
        try {
            // calling this method will throw an exception
            gfg.showResults();
        }
        catch (Exception e) {

            // Exception details using fillInStackTrace()
            e.printStackTrace();
        }
    }

    // method calling exceptionThrownMethod()
    // and when method returns Exception
    // it is calling fillInStackTrace() method
    public void showResults() throws Throwable
    {
        try {
            exceptionThrownMethod();
        }
        catch (Exception e) {
            e.printStackTrace();
            throw e.fillInStackTrace();
        }
    }

    // method throwing exception
    public void exceptionThrownMethod() throws Exception
    {
        throw new Exception("this is thrown from function1()");
    }
}
```

**输出:**

```java
java.lang.Exception: this is thrown from function1()
    at GFG.exceptionThrownMethod(GFG.java:35)
    at GFG.showResults(GFG.java:27)
    at GFG.main(GFG.java:13)

java.lang.Exception: this is thrown from function1()
    at GFG.showResults(GFG.java:30)
    at GFG.main(GFG.java:13)

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/lang/throwable . html](https://docs.oracle.com/javase/7/docs/api/java/lang/Throwable.html)