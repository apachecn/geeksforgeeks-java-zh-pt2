# Java 中的 OffsetDateTime withMinute()方法，带示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-with minute-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-withminute-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **withMinute()** 方法返回该 OffsetDateTime 的一个副本，其中一天中的小时按照参数中的指定进行了更改。

**语法:**

```java
public OffsetDateTime withMinute(int minute)
```

**参数:**该方法接受单个参数**分钟**，该参数指定要在结果中设置的小时分钟，范围从 0 到 59。

**返回值:**返回基于该日期的偏置日期时间，请求的分钟不为空。

**异常**:当小时的分钟值无效或一年中的某一天无效时，程序抛出**日期时间异常**。

以下程序说明了 *withMinute()* 方法:

**程序 1:**

```java
// Java program to demonstrate the withMinute() method

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

        // Changes the minute of day
        System.out.println("Date1 after altering minute of day: "
                           + date1.withMinute(20));
    }
}
```

**输出:**

```java
Date1: 2018-12-12T13:30:30+05:00
Date1 after altering minute of day: 2018-12-12T13:20:30+05:00

```

**程序二:**

```java
// Java program to demonstrate the withMinute() method

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
            System.out.println("Date1 after altering minute of day: "
                               + date1.withMinute(27));
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
Date1 after altering minute of day: 2018-12-12T13:27:30+05:00

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # with minute(int)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#withMinute(int))