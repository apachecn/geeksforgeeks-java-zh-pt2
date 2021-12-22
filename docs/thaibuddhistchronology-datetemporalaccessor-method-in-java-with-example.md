# Java 中的 thaibudhistoryesterday(临时日历)方法，示例

> 原文:[https://www . geeksforgeeks . org/thaibudhistderor-datetime alaccessor-method-in-Java-with-example/](https://www.geeksforgeeks.org/thaibuddhistchronology-datetemporalaccessor-method-in-java-with-example/)

**Java . time . chrono . ThaiBuddhist**类的 **date()** 方法用于根据 thaibudhistory 系统从另一个临时访问器对象获取本地日期。

**语法:**

```java
public LocalDate date(TemporalAccessor temporal)
```

**参数**:该方法以任意时态取值器的**对象为参数。**

**返回值:**该方法从另一个 TemporalAccessor 对象返回根据 ThaiBuddhist 日历系统的本地日期。

以下是说明**日期()**方法的示例:

**例 1:**

```java
// Java program to demonstrate
// date() method

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
            // by using date() method
            ThaiBuddhistDate date = crono.date(zonedate);

            // display the result
            System.out.println("ThaiBuddhistDate is: " + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
ThaiBuddhistDate is: ThaiBuddhist BE 2561-10-25

```

**例 2:**

```java
// Java program to demonstrate
// date() method

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
            // by using date() method
            ThaiBuddhistDate date = crono.date(localdate);

            // display the result
            System.out.println("ThaiBuddhistDate is: " + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
ThaiBuddhistDate is: ThaiBuddhist BE 2561-12-30

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibudhistorager . html # date-Java . time .时态. temporalacessor-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistChronology.html#date-java.time.temporal.TemporalAccessor-)