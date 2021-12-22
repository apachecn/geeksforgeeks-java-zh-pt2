# 带例子的 Java 中的 OffsetDateTime withDayOfYear()方法

> 原文:[https://www . geesforgeks . org/offsetdatetime-with dayof year-in-Java-method-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-withdayofyear-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **withDayOfYear()** 方法返回该 OffsetDateTime 的一个副本，其中年月日按照参数中的指定进行了更改。

**语法:**

```java
public OffsetDateTime withDayOfYear(int dayOfYear)
```

**参数:**该方法接受单个参数**day fyear**，该参数指定要在结果中设置的日期，该日期的范围为 1 到 365-366。

**返回值:**返回基于该日期的偏置日期时间，请求的日期为一年中的某一天，不为空。

**异常**:当一年中的某一天的值无效时，或者当某一年中的某一月的某一天无效时，程序会抛出**日期时间异常**。

下面的程序说明了*带 ayOfYear()* 的方法:

**程序 1:**

```java
// Java program to demonstrate the withDayOfYear() method

import java.time.OffsetDateTime;
import java.time.ZonedDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the date1
        OffsetDateTime date1
            = OffsetDateTime
                  .parse(
                      "2018-12-12T13:30:30+05:00");

        // Prints dates
        System.out.println("Date1: " + date1);

        // Changes the day of year
        System.out.println("Date1 after altering day-of-year: "
                           + date1.withDayOfYear(32));
    }
}
```

**输出:**

```java
Date1: 2018-12-12T13:30:30+05:00
Date1 after altering day-of-year: 2018-02-01T13:30:30+05:00

```

**程序二:**

```java
// Java program to demonstrate the withDayOfYear() method

import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {
        try {
            // Parses the date1
            OffsetDateTime date1
                = OffsetDateTime
                      .parse(
                          "2018-12-12T13:30:30+05:00");

            // Prints dates
            System.out.println("Date1: " + date1);

            // Changes the day of year
            System.out.println("Date1 after altering day-of-year: "
                               + date1.withDayOfYear(367));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
Date1: 2018-12-12T13:30:30+05:00
Exception: java.time.DateTimeException:
           Invalid value for DayOfYear
           (valid values 1 - 365/366): 367

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # withDayOfYear(int)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#withDayOfYear(int))