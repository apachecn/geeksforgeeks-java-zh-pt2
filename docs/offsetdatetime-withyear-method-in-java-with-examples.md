# 带示例的 Java 中的 OffsetDateTime withYear()方法

> 原文:[https://www . geesforgeks . org/offsetdatetime-with year-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-withyear-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **withYear()** 方法返回这个 OffsetDateTime 的一个副本，其中年份按照参数中的指定进行了更改。

**语法:**

```java
public OffsetDateTime withYear(int year)
```

**参数:**该方法接受单个参数**年份**，指定要在结果中设置的年份，范围从 *MIN_YEAR* 到 *MAX_YEAR* 。

**返回值:**返回基于该日期的偏置日期时间，请求年份不为空。

**异常**:当年份值无效时，程序抛出**日期时间异常**。

以下程序说明了 *withYear()* 方法:

**程序 1:**

```java
// Java program to demonstrate the withYear() method

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

        // Changes the year
        System.out.println("Date1 after altering year: "
                           + date1.withYear(2019));
    }
}
```

**输出:**

```java
Date1: 2018-12-12T13:30:30+05:00
Date1 after altering year : 2019-12-12T13:30:30+05:00

```

**程序二:**

```java
// Java program to demonstrate the withYear() method

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

        // Changes the year
        System.out.println("Date1 after altering year: "
                           + date1.withYear(2010));
    }
}
```

**输出:**

```java
Date1: 2018-12-12T13:30:30+05:00
Date1 after altering year: 2010-12-12T13:30:30+05:00

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # with year(int)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#withYear(int))