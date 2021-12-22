# Java 中可抛出的 printStackTrace()方法，带示例

> 原文:[https://www . geeksforgeeks . org/throwable-printstacktrace-method-in-Java-with-examples/](https://www.geeksforgeeks.org/throwable-printstacktrace-method-in-java-with-examples/)

### printStackTrace()

**Java.lang.Throwable 类**的 **printStackTrace()** 方法用于打印这个 Throwable 以及其他细节，如类名和行号，异常发生的地方意味着它的回溯。此方法在标准错误输出流上打印此可抛出对象的堆栈跟踪。
输出的第一行显示了由 toString()方法为该对象返回的相同字符串，这意味着异常类名，后面的几行表示之前由 fillInStackTrace()方法记录的数据。
**语法:**

```
public void printStackTrace()
```

**返回值:**这个方法不返回任何东西。
下面的程序说明了 Java.lang.Throwable 类的 printStackTrace 方法:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// the printStackTrace () Method.

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

            // print stack trace
            e.printStackTrace();
        }
    }

    // method which throws Exception
    public static void testException1()
        throws Exception
    {

        // create a ArrayIndexOutOfBoundsException Exception
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

**Output:** 

```
java.lang.Exception
    at GFG.testException1(File.java:36)
    at GFG.main(File.java:15)
Caused by: java.lang.ArrayIndexOutOfBoundsException
    at GFG.testException1(File.java:32)
    ... 1 more
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// the printStackTrace () Method.

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

            // print stack trace
            e.printStackTrace();
        }
    }

    // method which throws Exception
    public static void testException1()
        throws Exception
    {

        // create a ArrayIndexOutOfBoundsException Exception
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

**Output:** 

```
java.lang.Exception
    at GFG.testException1(File.java:36)
    at GFG.main(File.java:15)
Caused by: java.lang.ArrayIndexOutOfBoundsException
    at GFG.testException1(File.java:32)
    ... 1 more
```

### printStackTrace(PrintStream)

**Java.lang.Throwable 类**的**print stack trace(print stream s)**方法用于打印该 Throwable 以及其他详细信息，如指定打印流发生异常的类名和行号。此方法的工作方式与 printStackTrace()相同，但区别仅在于它打印到作为参数传递的指定打印流。
**语法:**

```
public void printStackTrace(PrintStream s)
```

**参数:**该方法接受**打印流 s** 作为参数，该参数是指定的打印流，我们要在该打印流中写入这个可抛出的细节。
**返回值:**这个方法不返回任何东西。
下面的程序说明了 Java.lang.Throwable 类的 printStackTrace 方法:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// the printStackTrace(PrintStream s) Method.

import java.io.*;

class GFG {

    // Main Method
    public static void main(String[] args)
        throws Exception
    {
        try {

            // create a array of Integers
            int[] i = new int[2];

            // try to add numbers to array
            i[2] = 3;
        }
        catch (Throwable e) {

            // print Stack Trace
            e.printStackTrace(System.out);
        }
    }
}
```

**Output:** 

```
java.lang.ArrayIndexOutOfBoundsException: 2
    at GFG.main(File.java:18)
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// the printStackTrace(PrintStream s) Method.

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

            // create printstream object
            PrintStream
                obj
                = new PrintStream(System.out);

            // print stack trace
            e.printStackTrace(obj);
        }
    }

    // method which throws Exception
    public static void testException1()
        throws Exception
    {

        throw new Exception("System is Down");
    }
}
```

**Output:** 

```
java.lang.Exception: System is Down
    at GFG.testException1(File.java:35)
    at GFG.main(File.java:15)
```

### printStackTrace(PrintWriter s)

**Java.lang.Throwable 类**的**print stack trace(print Writer s)**方法用于打印该 Throwable 以及其他详细信息，如类名称和行号，其中指定的打印编写器发生了异常。此方法的工作方式与 printStackTrace()相同，但不同之处仅在于它打印到作为参数传递的指定打印编写器。
**语法:**

```
public void printStackTrace(PrintWriter s)
```

**参数:**该方法接受 **PrintWriter s** 作为一个参数，该参数被指定为要写入该可丢弃细节的 PrintWriter。
**返回值:**这个方法不返回任何东西。
以下程序说明了可抛出类的 printStackTrace 方法:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// the printStackTrace(PrintWriter s) Method.

import java.io.*;

class GFG {

    // Main Method
    public static void main(String[] args)
        throws Exception
    {
        try {

            // divide two numbers
            int a = 74, b = 0;

            int c = a / b;
        }
        catch (Throwable e) {

            // Using a StringWriter,
            // to convert trace into a String:
            StringWriter sw = new StringWriter();

            // create a PrintWriter
            PrintWriter pw = new PrintWriter(sw);
            e.printStackTrace(pw);

            String error = sw.toString();

            System.out.println("Error:\n" + error);
        }
    }
}
```

**Output:** 

```
Error:
java.lang.ArithmeticException: / by zero
    at GFG.main(File.java:17)
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// the printStackTrace(PrintWriter s) Method.

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

            // Using a StringWriter,
            // to convert trace into a String:
            StringWriter sw = new StringWriter();

            // create a PrintWriter
            PrintWriter pw = new PrintWriter(sw);
            e.printStackTrace(pw);

            String error = sw.toString();

            System.out.println("Error:\n" + error);
        }
    }

    // method which throws Exception
    public static void testException1()
        throws Exception
    {
        throw new Exception(
            "Waiting for input but no response");
    }
}
```

**Output:** 

```
Error:
java.lang.Exception: Waiting for input but no response
    at GFG.testException1(File.java:38)
    at GFG.main(File.java:15)
```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/throwable . html # print stack trace()](https://docs.oracle.com/javase/10/docs/api/java/lang/Throwable.html#printStackTrace())
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/throwable . html # print stack trace(Java . io . print stream)](https://docs.oracle.com/javase/10/docs/api/java/lang/Throwable.html#printStackTrace(java.io.PrintStream))
[https://docs . Oracle . com/javase/10/docs/API/Java](https://docs.oracle.com/javase/10/docs/api/java/lang/Throwable.html#printStackTrace(java.io.PrintWriter))