# 带示例的 Java 中的 OffsetDateTime withDayOfMonth()方法

> 原文:[https://www . geeksforgeeks . org/offsetdatetime-with dayofmonth-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-withdayofmonth-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **withDayOfMonth()** 方法返回这个 OffsetDateTime 的一个副本，并按照参数中的指定更改月中的某一天。

**语法:**

```java
public OffsetDateTime withDayOfMonth(int dayOfMonth)
```

**参数:**此方法接受单个参数**日**，该参数指定要在结果中设置的月份，范围从 1 到 28-31。

**返回值:**返回基于该日期的偏置日期时间，请求日期不为空。

**异常**:当某月某日的值无效或某年某月某日的值无效时，程序会抛出**日期时间异常**。

以下程序说明了*与*的配合使用方法:

**程序 1:**

```java
// Java program to demonstrate the withDayOfMonth() method

import java.time.OffsetDateTime;

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

        // Changes the day of month
        System.out.println("Date1 after altering day-of-month: "
                           + date1.withDayOfMonth(20));
    }
}
```

**输出:**

```java
Date1: 2018-12-12T13:30:30+05:00
Date1 after altering day-of-month: 2018-12-20T13:30:30+05:00

```

**程序二** :

```java
// Java program to demonstrate the withDayOfMonth() method

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

            // Changes the day of month
            System.out.println("Date1 after altering day-of-month: "
                               + date1.withDayOfMonth(32));
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
           Invalid value for DayOfMonth (valid values 1 - 28/31): 32

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # with dayofmonth(int)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#withDayOfMonth(int))