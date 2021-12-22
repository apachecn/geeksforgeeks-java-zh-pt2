# Java 中的可抛出 initCause()方法，示例

> 原文:[https://www . geesforgeks . org/throwable-init cause-method-in-Java-with-examples/](https://www.geeksforgeeks.org/throwable-initcause-method-in-java-with-examples/)

**可抛出类**的 **initCause()** 方法用于初始化该可抛出的原因，指定的原因作为参数传递给 initCause()。实际上，原因是当异常发生时，引发这个可抛出对象的可抛出性。此方法只能调用一次。通常，此方法在构造函数中调用，或者在创建可抛出的之后立即调用。如果调用 Throwable 是通过使用 Throwable(Throwable)或 Throwable(String，Throwable)创建的，那么这个方法甚至不能被调用一次。

**语法:**

```java
public Throwable initCause?(Throwable cause)
```

**参数:**该方法接受**原因**作为代表该可投掷原因的参数。

**返回:**这个方法返回**对这个可抛出实例的引用。**

**异常:**此法抛出:

*   **IllegalArgumentException** If this is the cause, it can be thrown.
*   **illegal state exception** If this Throwable is created by throwable or throwable (String, throwable), or this method has been called on this throwable.

下面的程序说明了可抛出类的 initCause 方法:

**例 1:**

```java
// Java program to demonstrate
// the initCause() Method.

import java.io.*;

class GFG {

    // Main Method
    public static void main(String[] args)
        throws Exception
    {

        try {

            testException1();
        }

        catch (Throwable e) {

            System.out.println("Cause : "
                               + e.getCause());
        }
    }

    // method which throws Exception
    public static void testException1()
        throws Exception
    {

        // ArrayIndexOutOfBoundsException Exception
        // This exception will be used as a Cause
        // of another exception
        ArrayIndexOutOfBoundsException
            ae
            = new ArrayIndexOutOfBoundsException();

        // create a new Exception
        Exception ioe = new Exception();

        // initialize the cause and throw Exception
        ioe.initCause(ae);

        throw ioe;
    }
}
```

**输出:**

```java
Cause : java.lang.ArrayIndexOutOfBoundsException

```

**例 2:**

```java
// Java program to demonstrate
// the initCause() Method.

import java.io.*;

class GFG {

    // Main Method
    public static void main(String[] args)
        throws Exception
    {

        try {

            // add the numbers
            addPositiveNumbers(2, -1);
        }
        catch (Throwable e) {

            System.out.println("Cause : "
                               + e.getCause());
        }
    }

    // method which adds two positive number
    public static void addPositiveNumbers(int a, int b)
        throws Exception
    {

        // if Numbers are Positive
        // than add or throw Exception
        if (a < 0 || b < 0) {

            // create a Exception
            // when Numbers are not Positive
            // This exception will be used as a Cause
            // of another exception
            Exception
                ee
                = new Exception("Numbers are not Positive");

            // create a new Exception
            Exception anotherEXe = new Exception();

            // initialize the cause and throw Exception
            anotherEXe.initCause(ee);

            throw anotherEXe;
        }

        else {

            System.out.println(a + b);
        }
    }
}
```

**输出:**

```java
Cause : java.lang.Exception: Numbers are not Positive

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/throwable . html # init cause(Java . lang . throwable)](https://docs.oracle.com/javase/10/docs/api/java/lang/Throwable.html#initCause(java.lang.Throwable))