# Java 中可抛出的 toString()方法，示例

> 原文:[https://www . geesforgeks . org/throwable-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/throwable-tostring-method-in-java-with-examples/)

**Java.lang.Throwable 类**的 **toString()** 方法，用于返回该 Throwable 的字符串表示形式，该字符串表示形式由该对象的类名、冒号和空格(“:”)以及一个字符串组成，该字符串与调用该对象的 getLocalizedMessage()方法的结果相同，如果 getLocalizedMessage 返回 null，则只返回类名。

**语法:**

```
public String toString()
```

**返回值:**如果发生异常，该方法返回该可抛出的**字符串表示**。

下面的程序说明了 Throwable 类的 toString()方法:

**例 1:**

```
// Java program to demonstrate
// the toString() Method.

import java.io.*;

class GFG {

    // Main Method
    public static void main(String[] args)
        throws Exception
    {

        try {

            testException();
        }

        catch (Throwable e) {

            // print using tostring()
            System.out.println("Exception: "
                               + e.toString());
        }
    }

    // method which throws Exception
    public static void testException()
        throws Exception
    {

        throw new Exception("New Exception Thrown");
    }
}
```

**Output:**

```
Exception: java.lang.Exception: New Exception Thrown

```

**例 2:**

```
// Java program to demonstrate
// the toString() Method.

import java.io.*;

class GFG {

    // Main Method
    public static void main(String[] args)
        throws Exception
    {
        try {

            // divide two numbers
            int a = 4, b = 0;

            int c = a / b;
        }
        catch (Throwable e) {

            // print using tostring()
            System.out.println("Exception: "
                               + e.toString());
        }
    }
}
```

**Output:**

```
Exception: java.lang.ArithmeticException: / by zero

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/throwable . html # toString()](https://docs.oracle.com/javase/10/docs/api/java/lang/Throwable.html#toString())