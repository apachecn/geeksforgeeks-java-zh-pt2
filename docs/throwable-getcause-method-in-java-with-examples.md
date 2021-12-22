# Java 中可抛出的 getCause()方法，示例

> 原文:[https://www . geesforgeks . org/throwable-get cause-method-in-Java-with-examples/](https://www.geeksforgeeks.org/throwable-getcause-method-in-java-with-examples/)

**可抛出类**的 **getCause()** 方法是一种内置方法，用于在无法确定异常发生的原因时返回该可抛出或空的原因。此方法有助于获取由某个构造函数提供的原因，或者在创建之后用 initCause(Throwable)方法设置的原因。可抛出类的所有 PrintStackTrace 方法都调用 getCause()方法来确定可抛出或异常的原因。简单来说，可以说这个方法返回了异常发生的原因。

**语法:**

```java
public Throwable getCause()
```

**返回值:**该方法返回该可投掷物的**原因**，如果原因无法确定则返回**空**。

下面的程序演示了可抛出类的 getCause()方法:

**例 1:**

```java
// Java program to demonstrate
// the ensureCapacity() Method.

import java.io.*;

class GFG {

    // Main Method
    public static void main(String[] args)
        throws Exception
    {

        try {

            // divide the numbers
            divide(2, 0);
        }

        catch (ArithmeticException e) {

            System.out.println("Cause of Exception: "
                               + e.getCause());
        }
    }

    // method which divides two number
    public static void divide(int a, int b)
        throws Exception
    {

        try {

            // divide two numbers
            int i = a / b;
        }

        catch (ArithmeticException e) {

            // initializing new Exception with cause
            ArithmeticException exe = new ArithmeticException();

            exe.initCause(e);

            throw(exe);
        }
    }
}
```

**Output:**

```java
Cause of Exception: java.lang.ArithmeticException: / by zero

```

**例 2:**

```java
// Java program to demonstrate
// the ensureCapacity() Method.

import java.io.*;

class GFG {

    // Main Method
    public static void main(String[] args)
        throws Exception
    {

        try {

            // divide the numbers
            divide(2, 0);
        }

        catch (ArithmeticException e) {

            System.out.println("Cause of Exception : "
                               + e.getCause());
        }
    }

    // method which divides two number
    public static void divide(int a, int b)
        throws Exception
    {

        // divide two numbers
        int i = a / b;
    }
}
```

**Output:**

```java
Cause of Exception : null

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/throwable . html # getCause()](https://docs.oracle.com/javase/10/docs/api/java/lang/Throwable.html#getCause())