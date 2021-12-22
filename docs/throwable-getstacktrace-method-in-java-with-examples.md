# Java 中可抛出的 getStackTrace()方法，带示例

> 原文:[https://www . geeksforgeeks . org/throwable-getstacktrace-method-in-Java-with-examples/](https://www.geeksforgeeks.org/throwable-getstacktrace-method-in-java-with-examples/)

**可抛出类**的 **getStackTrace()** 方法，用于返回堆栈跟踪元素的数组，该数组是 printStackTrace()打印的堆栈跟踪信息。在堆栈跟踪元素的数组中(假设数组的长度为非零)，每个元素代表一个堆栈帧。数组的第一个元素意味着这个数组的第零个索引元素代表堆栈的顶部，这是序列中调用的最后一个方法，或者我们可以说这个第零个索引元素信息与 throwable 被创建和抛出的点有关。该数组的最后一个元素表示堆栈的底部，这是序列中调用的第一个方法。
在某些情况下，会返回堆栈跟踪中的一个或多个堆栈帧。此方法返回的数组将为 printStackTrace 打印的每一帧包含一个元素。对返回数组的任何更改都不会影响将来对此方法的调用。

**语法:**

```
public StackTraceElement[] getStackTrace()
```

**返回:**该方法返回**一个代表堆栈跟踪信息的堆栈跟踪元素数组**。

下面的程序说明了可投掷类的 **getStackTrace 方法:**

**例 1:**

```
// Java program to demonstrate
// the getStackTrace() Method.

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
            StackTraceElement[] stktrace
                = e.getStackTrace();

            // print element of stktrace
            for (int i = 0; i < stktrace.length; i++) {

                System.out.println("Index " + i
                                   + " of stack trace"
                                   + " array conatins = "
                                   + stktrace[i].toString());
            }
        }
    }

    // method which adds two positive number
    public static void addPositiveNumbers(int a, int b)
        throws Exception
    {

        // if Numbers are Positive
        // than add or throw Exception
        if (a < 0 || b < 0) {

            throw new Exception(
                "Numbers are not Positive");
        }

        else {

            System.out.println(a + b);
        }
    }
}
```

**Output:**

```
Index 0 of stack trace array conatins = GFG.addPositiveNumbers(File.java:48)
Index 1 of stack trace array conatins = GFG.main(File.java:18)

```

**例 2:**

```
// Java program to demonstrate
// the getStackTrace() Method.

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
            StackTraceElement[] stktrace
                = e.getStackTrace();

            // print element of stktrace
            for (int i = 0; i < stktrace.length; i++) {

                System.out.println("Index " + i
                                   + " of stack trace"
                                   + " array conatins = "
                                   + stktrace[i].toString());
            }
        }
    }

    // method which throws Exception
    // calling other method testException2
    public static void testException1()
        throws Exception
    {
        // This method second in series
        // of calling method which throw exception
        // so this will be second index element
        testException2();
    }

    // method which throws Exception
    // calling other method testException3
    public static void testException2()
        throws Exception
    {

        // This method calls a method
        // where exception is thrown
        // so this will be first index element
        testException3();
    }

    // method which throws IndexOutOfBoundsException
    public static void testException3()
        throws IndexOutOfBoundsException
    {

        // here exception thrown
        // so this will be Zeroth element
        throw new IndexOutOfBoundsException(
            "Forcefully Generated Exception");
    }
}
```

**Output:**

```
Index 0 of stack trace array conatins = GFG.testException3(File.java:68)
Index 1 of stack trace array conatins = GFG.testException2(File.java:58)
Index 2 of stack trace array conatins = GFG.testException1(File.java:46)
Index 3 of stack trace array conatins = GFG.main(File.java:17)

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/throwable . html # getstackrace()](https://docs.oracle.com/javase/10/docs/api/java/lang/Throwable.html#getStackTrace())