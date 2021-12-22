# Java 中可抛出的 getSuppressed()方法，示例

> 原文:[https://www . geesforgeks . org/throwable-get suppressed-method-in-Java-with-examples/](https://www.geeksforgeeks.org/throwable-getsuppressed-method-in-java-with-examples/)

**可抛出类**的 **getSuppressed()** 方法，用于返回一个数组，该数组包含所有被抑制的异常，以传递该异常，这种抑制通常由 try-with-resources 语句完成。为了传递异常如果没有异常被禁止或禁止，将返回一个禁止异常的空数组。对返回数组的任何更改都不会影响将来对此方法的调用。

**语法:**

```
public final Throwable[] getSuppressed()
```

**参数:**这个方法不接受任何东西作为参数。

**返回:**该方法返回一个包含所有被抑制的异常的**数组**。

下面的程序说明了可投掷类的**获取抑制()方法:**

**例 1:**

```
// Java program to demonstrate
// the getSuppressed() Method.

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

            // get StackTraceElements
            // using getStackTrace()
            Throwable[] suppExe
                = e.getSuppressed();

            // print element of suppExe
            for (int i = 0; i < suppExe.length; i++) {

                System.out.println("Suppressed Exceptions:");
                System.out.println(suppExe[i]);
            }
        }
    }

    // method which throws Exception
    public static void testException1()
        throws Exception
    {

        // creating a suppressed Exception
        Exception
            suppressed
            = new ArrayIndexOutOfBoundsException();

        // creating a IOException object
        final IOException ioe = new IOException();

        // adding suppressed Exception
        ioe.addSuppressed(suppressed);

        // throwing IOException
        throw ioe;
    }
}
```

**Output:**

```
Suppressed Exceptions:
java.lang.ArrayIndexOutOfBoundsException

```

**例 2:**

```
// Java program to demonstrate
// the getSuppressed() Method.

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

            // get StackTraceElements
            // using getStackTrace()
            Throwable[] suppExe
                = e.getSuppressed();

            // print element of stktrace
            System.out.println("Suppressed Exception Array"
                               + " length = "
                               + suppExe.length);
        }
    }

    // method which adds two positive number
    public static void addPositiveNumbers(int a, int b)
        throws Exception
    {

        // if Numbers are Positive
        // than add or throw Exception
        if (a < 0 || b < 0) {

            throw new Exception("Numbers are not Positive");
        }

        else {

            System.out.println(a + b);
        }
    }
}
```

**Output:**

```
Suppressed Exception Array length = 0

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/throwable . html # getSuppressed()](https://docs.oracle.com/javase/10/docs/api/java/lang/Throwable.html#getSuppressed())