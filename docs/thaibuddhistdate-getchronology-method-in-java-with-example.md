# Java 中的 ThaiBuddhistDate 年代()方法，示例

> 原文:[https://www . geeksforgeeks . org/thaibudhistate-get timer-method-in-Java-with-example/](https://www.geeksforgeeks.org/thaibuddhistdate-getchronology-method-in-java-with-example/)

**Java . time . chrono . ThaiBuddhiste**类的**get 年代学()**方法用于检索该日期所在的 thaibudhistat 日期的年代学。

**语法:**

```java
public ThaiBuddhistChronology getChronology()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回[这个](https://www.geeksforgeeks.org/this-reference-in-java/)泰国历史日期的年表。

以下是说明**获取时间表()**方法的示例:

**例 1:**

```java
// Java program to demonstrate
// getChronology() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate
                = ThaiBuddhistDate.now();

            // Getting the chronology of this date
            // by using getChronology() method
            ThaiBuddhistChronology crono
                = hidate.getChronology();

            // Display the result
            System.out.println(
                "ThaiBuddhistChronology: "
                + crono);
        }
        catch (DateTimeException e) {
            System.out.println(
                "Passed parameter can"
                + " not form a date");

            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
ThaiBuddhistChronology: ThaiBuddhist

```

**例 2:**

```java
// Java program to demonstrate
// getChronology() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // Creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate
                = ThaiBuddhistDate.of(2008, 04, 24);

            // Getting chronology of this date
            // by using getChronology() method
            ThaiBuddhistChronology crono
                = hidate.getChronology();

            // Display the result
            System.out.println(
                "ThaiBuddhistChronology: "
                + crono);
        }
        catch (DateTimeException e) {
            System.out.println(
                "Passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
ThaiBuddhistChronology: ThaiBuddhist

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibuddhistdate . html # GetError–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistDate.html#getChronology--)