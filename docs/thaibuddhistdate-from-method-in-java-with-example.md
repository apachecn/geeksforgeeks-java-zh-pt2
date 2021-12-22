# Java 中的 ThaiBuddhistDate from()方法，示例

> 原文:[https://www . geeksforgeeks . org/thaibudhistate-from-in-method-in-Java-with-example/](https://www.geeksforgeeks.org/thaibuddhistdate-from-method-in-java-with-example/)

**Java . time . chrono . thaibudhistate**类的 **from()** 方法用于根据特定时态对象的 thaibudhist 日历系统获取 thaibudhist 日期。

**语法:**

```java
public static ThaiBuddhistDate
      from(TemporalAccessor temporal)
```

**参数:**该方法取任意**时态访问器**的对象，在此基础上将形成 ThaiBuddhist 日期。

**返回值:**该方法根据指定时态对象的 thaibudhist 日历系统返回 thaibudhist 日期。

以下是举例说明从()方法的**:**

**例 1:**

```java
// Java program to demonstrate from() method

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
            // TemporalAccessor object
            ZonedDateTime
                zonedate
                = ZonedDateTime.parse(
                    "2018-10-25T23:12:31."
                    + "123+02:00[Europe/Paris]");

            // Creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate
                = ThaiBuddhistDate
                      .from(zonedate);

            // Display the result
            System.out.println(
                "ThaiBuddhistDate: "
                + hidate);
        }
        catch (DateTimeException e) {
            System.out.println(
                "Passed parameter can"
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
ThaiBuddhistDate: ThaiBuddhist BE 2561-10-25

```

**例 2:**

```java
// Java program to demonstrate from() method

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
            // TemporalAccessor object
            LocalDateTime
                localdate
                = LocalDateTime.parse(
                    "2018-12-30T19:34:50.63");

            // Creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate
                = ThaiBuddhistDate
                      .from(localdate);

            // Display the result
            System.out.println(
                "ThaiBuddhistDate: "
                + hidate);
        }
        catch (DateTimeException e) {
            System.out.println(
                "Passed parameter can"
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
ThaiBuddhistDate: ThaiBuddhist BE 2561-12-30

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibudhistate . html # from-Java . time . temporal accessor-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistDate.html#from-java.time.temporal.TemporalAccessor-)