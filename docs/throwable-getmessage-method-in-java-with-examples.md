# Java 中可抛出的 getMessage()方法，示例

> 原文:[https://www . geesforgeks . org/throwable-getmessage-method-in-Java-with-examples/](https://www.geeksforgeeks.org/throwable-getmessage-method-in-java-with-examples/)

**可投掷类**的 **getMessage()** 方法用于返回可投掷对象的详细消息，也可以为空。可以使用此方法获取异常的详细信息作为字符串值。

**语法:**

```java
public String getMessage()
```

**返回值:**该方法返回该可投掷实例的详细**消息**。

下面的程序演示了 java.lang.Throwable 类的 getMessage()方法

**例 1:**

```java
// Java program to demonstrate
// the getMessage() Method.

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

            System.out.println("Message String = "
                               + e.getMessage());
        }
    }

    // method which divide two numbers
    public static void divide(int a, int b)
        throws ArithmeticException
    {

        int c = a / b;

        System.out.println("Result:" + c);
    }
}
```

**Output:**

```java
Message String = / by zero

```

**例 2:**

```java
// Java program to demonstrate
// the getMessage() Method.

import java.io.*;

class GFG {

    // Main Method
    public static void main(String[] args)
        throws Exception
    {

        try {

            test();
        }

        catch (Throwable e) {

            System.out.println("Message of Exception : "
                               + e.getMessage());
        }
    }

    // method which throws UnsupportedOperationException
    public static void test()
        throws UnsupportedOperationException
    {

        throw new UnsupportedOperationException();
    }
}
```

**Output:**

```java
Message of Exception : null

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/throwable . html # getMessage()](https://docs.oracle.com/javase/10/docs/api/java/lang/Throwable.html#getMessage())