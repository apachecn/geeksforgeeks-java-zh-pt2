# Java 中的 thaibudhistechronic local datetime()方法，示例

> 原文:[https://www . geeksforgeeks . org/thaibudhistechr-local datetime-Java 中的方法-带示例/](https://www.geeksforgeeks.org/thaibuddhistchronology-localdatetime-method-in-java-with-example/)

**Java . time . chrono . ThaiBuddhist**类的 **localDateTime()** 方法用于根据 thaibudhistory 系统从时态访问器的任何其他对象中检索本地日期和时间。

**语法:**

```java
public ChronoLocalDateTime localDateTime
               (TemporalAccessor temporal)

```

**参数**:该方法以任意时态取值器的**对象为参数。**

**返回值:**该方法从时态访问器的任何其他对象返回根据泰国历系统的**本地日期**和时间。

以下是说明 **localDateTime()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// localDateTime() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate
                = ThaiBuddhistDate.now();

            // getting ThaiBuddhistChronology
            // used in ThaiBuddhistDate
            ThaiBuddhistChronology crono
                = hidate.getChronology();

            // creating and initializing
            // TemporalAccessor object
            ZonedDateTime zonedate
                = ZonedDateTime.parse(
                    "2018-10-25T23:12:31."
                    + "123+02:00[Europe/Paris]");

            // getting ThaiBuddhistDate for the
            // given TemporalAccessor object
            // by using localDateTime() method
            ChronoLocalDateTime<ThaiBuddhistDate> date
                = crono.localDateTime(zonedate);

            // display the result
            System.out.println("ThaiBuddhistDate is: "
                               + date);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
ThaiBuddhistDate is: ThaiBuddhist BE 2561-10-25T23:12:31.123

```

**例 2:**

```java
// Java program to demonstrate
// localDateTime() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate
                = ThaiBuddhistDate.now();

            // getting ThaiBuddhistChronology
            // used in ThaiBuddhistDate
            ThaiBuddhistChronology crono
                = hidate.getChronology();

            // creating and initializing
            // TemporalAccessor object
            LocalDateTime localdate
                = LocalDateTime
                      .parse("2018-12-30T19:34:50.63");

            // getting ThaiBuddhistDate for the
            // given TemporalAccessor object
            // by using localDateTime() method
            ChronoLocalDateTime<ThaiBuddhistDate> date
                = crono.localDateTime(localdate);

            // display the result
            System.out.println("ThaiBuddhistDate is: "
                               + date);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
ThaiBuddhistDate is: ThaiBuddhist BE 2561-12-30T19:34:50.630

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibudhistechrome . html # localDateTime-Java . time . temporal accessor-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistChronology.html#localDateTime-java.time.temporal.TemporalAccessor-)