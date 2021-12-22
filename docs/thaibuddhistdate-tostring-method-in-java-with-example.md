# Java 中的 ThaiBuddhistDate toString()方法，示例

> 原文:[https://www . geeksforgeeks . org/thaibudhistate-tostring-method-in-Java-with-example/](https://www.geeksforgeeks.org/thaibuddhistdate-tostring-method-in-java-with-example/)

类的 **toString()** 方法用于以字符串格式表示这个 ThaiBuddhist 日期。该方法只返回该对象的文本格式，该格式易于阅读，并包含所需的日期信息。

**语法:**

```java
public String toString()
```

**覆盖:**ToString()方法覆盖了 Java 中的[对象类。](https://www.geeksforgeeks.org/object-class-in-java/)

**参数**:该方法不接受任何参数作为参数。

**返回值:**该方法以字符串形式返回**泰国历史日期**。

以下程序说明了 **toString()** 方法:

**程序 1:**

```java
// Java program to demonstrate
// toString() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // Creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate
                = ThaiBuddhistDate.now();

            // Getting string represntation
            // of ThaiBuddhist date
            // by using toString() method
            String date = hidate.toString();

            // Display the result
            System.out.println(
                "ThaiBuddhistdate : "
                + date);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: "
                + e);
        }
    }
}
```

**输出:**

```java
ThaiBuddhistdate : ThaiBuddhist BE 2563-05-08

```

**程序二:**

```java
// Java program to demonstrate
// toString() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // Creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate
                = ThaiBuddhistDate.of(
                    1345, 05, 23);

            // Getting string represntation
            // of ThaiBuddhist date
            // by using toString() method
            String date = hidate.toString();

            // Display the result
            System.out.println(
                "ThaiBuddhistdate : "
                + date);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: "
                + e);
        }
    }
}
```

**输出:**

```java
ThaiBuddhistdate : ThaiBuddhist BE 1345-05-23

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibuddhistdate . html # toString–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistDate.html#toString--)