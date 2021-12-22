# Java 中的 OffsetDateTime withMonth()方法，带示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-with month-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-withmonth-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **withMonth()** 方法返回这个 OffsetDateTime 的一个副本，其中一年中的月份按照参数中的指定进行了更改。

**语法:**

```
public OffsetDateTime withMonth(int month)
```

**参数:**该方法接受单个参数**月**，该参数指定要在结果中设置的月份，范围从 1 到 12。

**返回值:**返回基于该日期的偏置日期时间，请求的是一年中的月份，不为空。

**异常**:当年月值无效时，程序抛出**日期时间异常**。

以下程序说明了 *withMonth()* 方法:

**程序 1:**

```
// Java program to demonstrate the withMonth() method

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

        // Changes the month-of-year
        System.out.println("Date1 after altering month-of-year: "
                           + date1.withMonth(10));
    }
}
```

**输出:**

```
Date1: 2018-12-12T13:30:30+05:00
Date1 after altering month-of-year: 2018-10-12T13:30:30+05:00

```

**程序二:**

```
// Java program to demonstrate the withMonth() method

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

            // Changes the minute of day
            System.out.println("Date1 after altering month-of-year: "
                               + date1.withMonth(27));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```
Date1: 2018-12-12T13:30:30+05:00
Exception: java.time.DateTimeException: Invalid value for MonthOfYear (valid values 1 - 12): 27

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # with month(int)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#withMonth(int))