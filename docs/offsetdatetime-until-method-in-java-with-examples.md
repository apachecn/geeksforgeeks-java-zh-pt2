# Java 中的 OffsetDateTime 直到()方法，示例

> 原文:[https://www . geeksforgeeks . org/offsetdatetime-to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-until-method-in-java-with-examples/)

**直到()**方法的 **OffsetDateTime** 类用来计算两个 OffsetDateTime 对象之间的时间量，使用的是 TemporalUnit。起点和终点是这样的，指定的 OffsetDateTime 作为参数传递。如果结束在开始之前，结果将是否定的。计算返回一个整数，表示两个 OffsetDateTime 之间的完整单位数。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public long until(Temporal endExclusive, TemporalUnit unit)

```

**参数:**该方法接受两个参数 endExclusive，endExclusive 为结束日期，Exclusive 转换为 OffsetDateTime，unit 为计量金额的单位。

**返回值:**这个方法返回这个 OffsetDateTime 和结束 OffsetDateTime 之间的时间量。

**异常:**该方法抛出以下异常:

*   datetime exception–如果无法计算金额，或者结束时态无法转换为 OffsetDateTime。
*   unsupportedtemporaltypexception–如果设备不受支持。
*   算术异常–如果出现数字溢出。

以下程序说明了直到()方法:
**程序 1:**

```java
// Java program to demonstrate
// OffsetDateTime.until() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create OffsetDateTime objects
        OffsetDateTime date1 = OffsetDateTime.parse("2018-12-12T13:30:30+05:00");
        OffsetDateTime date2 = OffsetDateTime.parse("2015-12-12T13:30:30+05:00");

        // apply until method of OffsetDateTime class
        long result
            = date2.until(date1,
                          ChronoUnit.MONTHS);

        // print results
        System.out.println("Result in MONTHS: "
                           + result);
    }
}
```

**Output:**

```java
Result in MONTHS: 36

```

**程序 2:**

```java
// Java program to demonstrate
// OffsetDateTime.until() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create OffsetDateTime objects
        OffsetDateTime date1 = OffsetDateTime.parse("2018-12-12T13:30:30+05:00");
        OffsetDateTime date2 = OffsetDateTime.parse("2015-12-12T13:30:30+05:00");

        // apply until method of OffsetDateTime class
        long result
            = date1.until(date2,
                          ChronoUnit.YEARS);

        // print results
        System.out.println("Result in YEARS: "
                           + result);
    }
}
```

**Output:**

```java
Result in YEARS: -3

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html #直到(java.time.temporal.Temporal，Java . time . temporal unit)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#until(java.time.temporal.Temporal, java.time.temporal.TemporalUnit))