# 带示例的 Java 中的 OffsetDateTime withHour()方法

> 原文:[https://www . geeksforgeeks . org/offsetdatetime-with our-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-withhour-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的**withour()**方法返回该 OffsetDateTime 的副本，并按照参数中的指定更改一天中的小时。

**语法:**

```
public OffsetDateTime withHour(int hour)
```

**参数:**该方法接受单个参数**小时**，该参数指定要在结果中设置的一天中的小时，范围从 0 到 23。

**返回值:**返回基于该日期的偏置日期时间，请求一天中的小时，不为空。

**异常**:当一天中的小时值无效或一年中的某一天无效时，程序会抛出**日期时间异常**。

下面的程序说明了*与*的方法:

**程序 1:**

```
// Java program to demonstrate the withHour() method

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

        // Changes the hour of day
        System.out.println("Date1 after altering hour of the day: "
                           + date1.withHour(20));
    }
}
```

**输出:**

```
Date1: 2018-12-12T13:30:30+05:00
Date1 after altering hour of the day: 2018-12-12T20:30:30+05:00

```

**程序二:**

```
// Java program to demonstrate the withHour() method

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

            // Changes the hour of day
            System.out.println("Date1 after altering hour of the day: "
                               + date1.withHour(27));
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
Exception: java.time.DateTimeException:
           Invalid value for HourOfDay (valid values 0 - 23): 27

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # withour(int)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#withHour(int))