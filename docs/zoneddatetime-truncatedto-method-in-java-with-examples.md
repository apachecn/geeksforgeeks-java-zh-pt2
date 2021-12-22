# Java 中的 ZonedDateTime 截断 To()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-shopped to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-truncatedto-method-in-java-with-examples/)

**区域数据时间**类的**截断到()**方法用于以指定的单位返回该区域数据时间的值。此方法采用参数“单位”，即该区域的时间将被截断到的单位。它返回一个截断的不可变区域数据时间，其值以指定的单位表示。

**语法:**

```java
public ZonedDateTime truncatedTo(TemporalUnit unit)

```

**参数:**该方法接受一个单参数**单位**，该单位是该区域数据时间被截断的单位。它不应为空。

**返回值:**该方法返回一个**不可变的截断区域数据时间**，该值以指定的单位表示。

**异常:**此方法抛出以下异常:

*   **日期时间异常:**(中文)。
*   **Unsupported company** is not supported.

下面的程序说明了截断到()方法:

**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.truncatedTo() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zonedDT
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // print ZonedDateTime
        System.out.println("ZonedDateTime before"
                           + " truncate: "
                           + zonedDT);

        // truncate to ChronoUnit.HOURS
        // means unit smaller than Hour
        // will be Zero
        ZonedDateTime returnvalue
            = zonedDT.truncatedTo(ChronoUnit.HOURS);

        // print result
        System.out.println("ZonedDateTime after "
                           + " truncate: "
                           + returnvalue);
    }
}
```

**输出:**

```java
ZonedDateTime before truncate: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
ZonedDateTime after  truncate: 2018-12-06T19:00+05:30[Asia/Calcutta]

```

**程序二:**

```java
// Java program to demonstrate
// ZonedDateTime.truncatedTo() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zonedDT
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // print ZonedDateTime
        System.out.println("ZonedDateTime before"
                           + " truncate: "
                           + zonedDT);

        // truncate to ChronoUnit.DAYS
        // means unit smaller than DAY
        // will be Zero
        ZonedDateTime returnvalue
            = zonedDT.truncatedTo(ChronoUnit.DAYS);

        // print result
        System.out.println("ZonedDateTime after "
                           + " truncate: "
                           + returnvalue);
    }
}
```

**输出:**

```java
ZonedDateTime before truncate: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
ZonedDateTime after  truncate: 2018-12-06T00:00+05:30[Asia/Calcutta]

```

**参考:**[https://docs . Oracle . com/javae/10/docs/API/Java/time/zoneddatetime . html # withzonesame instant(Java . time . zoneid)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#withZoneSameInstant(java.time.ZoneId))