# Java 中可抛出的 setStackTrace()方法，带示例

> 原文:[https://www . geeksforgeeks . org/throwable-setstacktrace-method-in-Java-with-examples/](https://www.geeksforgeeks.org/throwable-setstacktrace-method-in-java-with-examples/)

**Throwable 类的**setstack trace(stack trace element【】stack trace)**方法是**用来将堆栈跟踪元素设置到这个 Throwable 对象，这个堆栈跟踪将由 getStackTrace()返回，并由 printStackTrace()和相关方法打印。此方法允许用户重写默认堆栈跟踪，该跟踪在构造可抛出对象时由 fillInStackTrace()生成，或者在从序列化流中读取可抛出对象时反序列化。
如果任何 Throwable 的堆栈跟踪不可写，那么调用此方法除了验证其参数之外没有任何作用。
**语法:**

```java
public void 
    setStackTrace(StackTraceElement[] stackTrace)
```

**参数:**该方法只接受一个参数 **stackTrace** ，即与该可投掷物关联的堆栈微量元素。
**返回:**此方法不返回任何内容。
以下程序说明了 setStackTrace()方法:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// the setStackTrace () Method.

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

            // access to the stack trace
            StackTraceElement[] trace = e.getStackTrace();

            System.out.println(trace[0].toString());
        }
    }

    // method which throws Exception
    public static void testException1()
        throws Exception
    {

        // create a new Exception
        Exception ex = new Exception();

        StackTraceElement[] trace = new StackTraceElement[] {
            new StackTraceElement("ClassNameOfExe",
                                  "methodNameOfExe",
                                  "fileNameOfExe",
                                  10)
        };

        // sets the stack trace elements
        ex.setStackTrace(trace);

        // throw the Throwable[
        throw ex;
    }
}
```

**Output:** 

```java
ClassNameOfExe.methodNameOfExe(fileNameOfExe:10)
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// the setStackTrace () Method.

import java.io.*;

class GFG {

    // Main Method
    public static void main(String[] args)
        throws Exception
    {

        try {

            Exceptiontest();
        }

        catch (Throwable e) {

            // access to the stack trace
            StackTraceElement[] trace = e.getStackTrace();

            System.out.println("StackTraceElement length :"
                               + trace.length);

            for (int i = 0; i < trace.length; i++) {

                System.out.println("Stack Trace at index "
                                   + i + " : "
                                   + trace[i]);
            }
        }
    }

    // method which throws Exception
    public static void Exceptiontest()
        throws Exception
    {

        // create a new Exception
        ArrayStoreException ex = new ArrayStoreException();

        StackTraceElement[] trace = new StackTraceElement[] {
            new StackTraceElement("ClassName1", "methodName1",
                                  "fileName1", 10),
            new StackTraceElement("ClassName2", "methodName2",
                                  "fileName2", 20),
            new StackTraceElement("ClassName3", "methodName3",
                                  "fileName3", 14)
        };

        // sets the stack trace elements
        ex.setStackTrace(trace);

        throw ex;
    }
}
```

**Output:** 

```java
StackTraceElement length :3
Stack Trace at index 0 : ClassName1.methodName1(fileName1:10)
Stack Trace at index 1 : ClassName2.methodName2(fileName2:20)
Stack Trace at index 2 : ClassName3.methodName3(fileName3:14)
```

参考文献:
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/throwable . html # setStackTrace(Java . lang . stacktrace element % 5B % 5D)](https://docs.oracle.com/javase/10/docs/api/java/lang/Throwable.html#setStackTrace(java.lang.StackTraceElement%5B%5D))