# Java 中的 ZonedDateTime 减()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-减去方法-in-java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-minus-method-in-java-with-examples/)

在 ZonedDateTime 类中，根据传递给它的参数，有两种类型的减()方法。

### 减(长数量到子管道，临时单位)

**减()**方法的一个 **ZonedDateTime** 类用来返回这个日期时间的一个副本，并减去指定数量的单位。如果由于不支持该单位或其他原因而无法减去该金额，则会引发异常。

**语法:**

```java
public ZonedDateTime minus(long amountToSubtract,
                           TemporalUnit unit)

```

**参数:**该方法接受两个参数:

*   **amountToSubtract:** 是要从结果中减去的单位的数量，可以是负数
*   **单位:**是要减去的量的单位。

**返回值:**该方法根据该日期时间减去指定的金额返回**区域时间**。

**异常:**该方法抛出以下异常:

*   **日期时间异常**:如果不能做减法，
*   **unsupportedtemporaltypexception**:如果不支持该单元。
*   **算术异常**:如果出现数值溢出。

下面的程序说明了减()方法:

**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.minus() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zonedlt
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // subtract 30 Months to ZonedDateTime
        ZonedDateTime value
            = zonedlt.minus(30, ChronoUnit.MONTHS);

        // print result
        System.out.println("ZonedDateTime after"
                           + " subtracting Months:\n "
                           + value);
    }
}
```

**Output:**

```java
ZonedDateTime after subtracting Months:
 2016-06-06T19:21:12.123+05:30[Asia/Calcutta]

```

### 减(临时金额到小计)

**减()**方法的一个 **ZonedDateTime** 类用来返回这个日期时间的一个副本，其中指定的数量减去日期时间。该金额通常为“期间”或“持续时间”，但也可以是实现临时计费界面的任何其他类型。

**语法:**

```java
public ZonedDateTime minus(TemporalAmount amountTosubtract)

```

**参数:**此方法接受一个单参数 **amountTosubtract** 为要减去的量，不应为空。

**返回值:**该方法基于该日期时间减去非空值返回**区域时间**

**异常:**该方法抛出以下异常:

*   **日期时间异常**:如果不能做减法< /li
*   **算术异常**:如果出现数值溢出

下面的程序说明了减()方法:

**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.minus() method

import java.time.*;
public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zonedlt
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // subtract 10 Days to ZonedDateTime
        ZonedDateTime value
            = zonedlt.minus(Period.ofDays(10));

        // print result
        System.out.println("ZonedDateTime after"
                           + " subtracting Days:\n "
                           + value);
    }
}
```

**Output:**

```java
ZonedDateTime after subtracting Days:
 2018-11-26T19:21:12.123+05:30[Asia/Calcutta]

```

**参考:**

*   [https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html #减(java.time .时态. tempalamount)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#minus(java.time.temporal.TemporalAmount))
*   [https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html #减(long，Java . time . temporalunit)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#minus(long, java.time.temporal.TemporalUnit))