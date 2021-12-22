# Java 中的 OffsetDateTime minusDays()方法，带示例

> 原文:[https://www . geesforgeks . org/offset datetime-mins days-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-minusdays-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **minusDays()** 方法返回这个 OffsetDateTime 的一个副本，从解析的日期和时间中减去指定的天数。

**语法:**

```
public OffsetDateTime minusDays(long days)
```

**参数:**该方法接受单个参数**天数**，该参数指定要从解析的日期中减去的天数。它也可以是负数，在这种情况下，它会加上天数。

**返回值:**根据这个日期时间返回一个 OffsetDateTime，减去天数后不为空。

**异常:**当超出支持的数据和时间范围时，程序抛出**日期时间异常**。

以下程序说明了*天数()*方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the minusDays() method

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

        // Subtracts the number of days
        System.out.println("Date1 after subtracting days: "
                           + date1.minusDays(140));
    }
}
```

**Output:** 

```
Date1: 2018-12-12T13:30:30+05:00
Date1 after subtracting days: 2018-07-25T13:30:30+05:00
```

**程序 2** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the minusDays() method
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

        // Subtracts the number of days
        System.out.println("Date1 after subtracting days: "
                           + date1.minusDays(-120));
    }
}
```

**Output:** 

```
Date1: 2018-12-12T13:30:30+05:00
Date1 after subtracting days: 2019-04-11T13:30:30+05:00
```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # minusDays(长)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#minusDays(long))