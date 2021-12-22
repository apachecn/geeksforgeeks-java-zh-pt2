# Java 中的 OffsetDateTime minusYears()方法，带示例

> 原文:[https://www . geesforgeks . org/offset datetime-mins years-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-minusyears-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **minusYears()** 方法返回这个 OffsetDateTime 的一个副本，从解析的日期和时间中减去指定的年数。

**语法:**

```java
public OffsetDateTime minusYears(long years)
```

**参数:**该方法接受单个参数**年份**，该参数指定要从解析日期中减去的年份。它也可以是负数，在这种情况下，它会加上年数。

**返回值:**根据这个日期时间返回一个 OffsetDateTime，减去年份，不为空。

**异常**:超出支持的数据和时间范围，程序抛出**日期时间异常**。

下面的程序说明了*负年()*方法:

**程序 1:**

```java
// Java program to demonstrate the minusYears() method

import java.time.OffsetDateTime;
import java.time.ZonedDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the date1
        OffsetDateTime date1
            = OffsetDateTime
                  .parse("2018-12-12T13:30:30+05:00");

        // Prints dates
        System.out.println("Date1: " + date1);

        // Subtracts the number of years
        System.out.println("Date1 after subtracting years: "
                           + date1.minusYears(-120));
    }
}
```

**输出:**

```java
Date1: 2018-12-12T13:30:30+05:00
Date1 after subtracting years: 2138-12-12T13:30:30+05:00

```

**程序二** :

```java
// Java program to demonstrate the minusYears() method

import java.time.OffsetDateTime;
import java.time.ZonedDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the date1
        OffsetDateTime date1
            = OffsetDateTime
                  .parse("2018-12-12T13:30:30+05:00");

        // Prints dates
        System.out.println("Date1: "
                           + date1);

        // Subtracts the number of years
        System.out.println("Date1 after subtracting years: "
                           + date1.minusYears(140));
    }
}
```

**输出:**

```java
Date1: 2018-12-12T13:30:30+05:00
Date1 after subtracting years: 1878-12-12T13:30:30+05:00

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # MINUS years(长)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#minusYears(long))