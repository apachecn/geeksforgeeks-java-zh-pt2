# Java 中(LocalDate，LocalTime)方法的 OffsetDateTime，示例

> 原文:[https://www . geeksforgeeks . org/offsetdatetime-of localdate-local time-in-Java-method-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-oflocaldate-localtime-method-in-java-with-examples/)

Java 中 **OffsetDateTime** 类的【本地日期、本地时间、区域偏移偏移】方法的**用于根据给定的日期、时间和偏移实例创建 **OffsetDateTime** 的实例。此方法使用指定的本地日期、本地时间和偏移量创建一个 OffsetDateTime。**

**语法:**

```java
public static OffsetDateTime of(LocalDate date,
                                LocalTime time,
                                ZoneOffset offset)

```

**参数:**该方法接受三个参数:

*   **日期**–代表当地日期。
*   **时间**–代表当地时间。
*   **偏移**–表示区域偏移。

**返回值:**该方法返回**偏移日期时间**。

**异常:**此方法不抛出任何异常。

下面的程序说明了 Java 中 OffsetDateTime 类的(LocalDate，LocalTime，ZoneOffset)方法:

**程序 1:**

```java
// Java program to demonstrate
// OffsetDateTime
// of(LocalDate, LocalTime, ZoneOffset) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // Create LocalDate object
        LocalDate date
            = LocalDate.parse(
                "2020-05-28");

        // Create LocalTime object
        LocalTime time
            = LocalTime.parse(
                "03:50:40");

        // Create OffsetDateTime object
        OffsetDateTime offsetdatetime
            = OffsetDateTime.of(
                date, time, ZoneOffset.UTC);

        // Print date-time
        System.out.println("DATE-TIME: "
                           + offsetdatetime);
    }
}
```

**Output:**

```java
DATE-TIME: 2020-05-28T03:50:40Z

```

**程序 2:**

```java
// Java program to demonstrate
// OffsetDateTime
// of(LocalDate, LocalTime, ZoneOffset) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // Create LocalDate object
        LocalDate date
            = LocalDate.of(
                2020, 5, 28);

        // Create LocalTime object
        LocalTime time
            = LocalTime.of(
                3, 50, 40);

        // Create OffsetDateTime object
        OffsetDateTime offsetdatetime
            = OffsetDateTime.of(
                date, time, ZoneOffset.UTC);

        // Print date-time
        System.out.println("DATE-TIME: "
                           + offsetdatetime);
    }
}
```

**Output:**

```java
DATE-TIME: 2020-05-28T03:50:40Z

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # of(Java . time . local date，java.time.LocalTime，java.time.ZoneOffset)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#of(java.time.LocalDate, java.time.LocalTime, java.time.ZoneOffset))