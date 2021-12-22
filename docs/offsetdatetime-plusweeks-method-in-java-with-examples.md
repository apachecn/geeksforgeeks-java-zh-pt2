# Java 中的 OffsetDateTime plusWeeks()方法，带示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-plusweeks-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-plusweeks-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **plusWeeks()** 方法返回这个 OffsetDateTime 的一个副本，指定的周数被添加到解析的日期和时间中。

**语法:**

```java
public OffsetDateTime plusWeeks(long weeks)

```

**参数:**该方法接受单个参数**周**，该参数指定要添加到解析日期的周。它也可以是负的，在这种情况下，它会减去周数。

**返回值:**根据这个日期时间返回一个 OffsetDateTime，加上星期，不为空。

**异常**:超出支持的数据和时间范围，程序抛出**日期时间异常**。

以下程序说明了 *plusWeeks()* 方法:

**程序 1:**

```java
// Java program to demonstrate the plusWeeks() method

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

        // Subtracts the number of weeks
        System.out.println("Date1 after adding weeks: "
                           + date1.plusWeeks(-120));
    }
}
```

**输出:**

```java
Date1: 2018-12-12T13:30:30+05:00
Date1 after adding weeks: 2016-08-24T13:30:30+05:00

```

**程序二** :

```java
// Java program to demonstrate the plusWeeks() method

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

        // Subtracts the number of weeks
        System.out.println("Date1 after adding weeks: "
                           + date1.plusWeeks(140));
    }
}
```

**输出:**

```java
Date1: 2018-12-12T13:30:30+05:00
Date1 after adding weeks: 2021-08-18T13:30:30+05:00

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # plusWeeks(长)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#plusWeeks(long))