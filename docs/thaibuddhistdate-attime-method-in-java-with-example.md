# Java 中的 ThaiBuddhistDate atTime()方法，示例

> 原文:[https://www . geeksforgeeks . org/thaibudhistate-attime-method-in-Java-with-example/](https://www.geeksforgeeks.org/thaibuddhistdate-attime-method-in-java-with-example/)

**Java . time . chrono . thaibudhistate**类的 **atTime()** 方法用于根据 thaibudhist 日历系统从另一个 TemporalAccessor 对象获取 thaibudhist 日期和时间。

**语法:**

```java
public ChronoLocalDateTime 
       atTime(LocalTime localTime)
```

**参数:**该方法以 [LocalTime](https://www.geeksforgeeks.org/localtime-now-method-in-java-with-examples/) 类型的对象为参数。

**返回值:**这个方法通过将这个 ThaiBuddhist 日期和经过的本地时间相加，返回 ChronoLocalDateTime。一个时空日期时间是一个日期时间，它在任意的时间表中没有时区。它旨在用于高级全球化用例。

以下是说明 **atTime()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// atTime() method

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

            // Creating and initializing
            // TemporalAccessor object
            LocalTime localtime
                = LocalTime.now();

            // Getting the Chrono Local date
            // time by using atTime() method
            ChronoLocalDateTime<ThaiBuddhistDate> date
                = hidate.atTime(localtime);

            // Display the result
            System.out.println(
                "Chrono LocalDateTime is: "
                + date);
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
Chrono LocalDateTime is:
 ThaiBuddhist BE 2563-05-03T13:16:55.338

```

**例 2:**

```java
// Java program to demonstrate
// atTime() method

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

            // Creating and initializing
            // TemporalAccessor object
            LocalTime localtime
                = LocalTime.of(8, 20);

            // Getting the Chrono Local date
            // time by using atTime() method
            ChronoLocalDateTime<ThaiBuddhistDate> date
                = hidate.atTime(localtime);

            // Display the result
            System.out.println(
                "Chrono LocalDateTime is: "
                + date);
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
Chrono LocalDateTime is:
 ThaiBuddhist BE 2563-05-03T08:20

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibudhistate . html # atTime-Java . time . local time-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistDate.html#atTime-java.time.LocalTime-)