# Java 中的 OffsetDateTime minusMinutes()方法，带示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-mins minutes-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-minusminutes-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的**minutations()**方法返回这个 OffsetDateTime 的一个副本，从解析的日期和时间中减去指定的分钟数。

**语法:**

```
public OffsetDateTime minusMinutes(long minutes)
```

**参数:**该方法接受单个参数**分钟**，该参数指定要从解析的日期中减去的分钟数。它也可以是负数，在这种情况下，它会加上分钟数。

**返回值:**根据该日期时间返回偏移日期时间，减去分钟，不为空。

**异常:**当超出支持的数据和时间范围时，程序抛出**日期时间异常**。

以下程序说明了*分钟()*方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the minusMinutes() method

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

        // Subtracts the number of minutes
        System.out.println("Date1 after subtracting minutes: "
                           + date1.minusMinutes(-120));
    }
}
```

**Output:** 

```
Date1: 2018-12-12T13:30:30+05:00
Date1 after subtracting minutes: 2018-12-12T15:30:30+05:00
```

**程序 2** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the minusMinutes() method
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

        // Subtracts the number of minutes
        System.out.println("Date1 after subtracting minutes: "
                           + date1.minusMinutes(140));
    }
}
```

**Output:** 

```
Date1: 2018-12-12T13:30:30+05:00
Date1 after subtracting minutes: 2018-12-12T11:10:30+05:00
```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # minutes(长)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#minusMinutes(long))