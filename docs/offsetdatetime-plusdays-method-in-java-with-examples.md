# Java 中的 OffsetDateTime plusDays()方法，带示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-plus days-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-plusdays-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **plusDays()** 方法返回这个 OffsetDateTime 的一个副本，指定的天数被添加到解析的日期和时间中。

**语法:**

```
public OffsetDateTime plusDays(long days)

```

**参数:**该方法接受单个参数**天数**，该参数指定要添加到解析日期的天数。它也可以是负的，在这种情况下，它会减去天数。

**返回值:**根据这个日期时间返回一个偏置日期时间，加上天数，不为空。

**异常**:超出支持的数据和时间范围，程序抛出**日期时间异常**。

以下程序说明了 *plusDays()* 方法:

**程序 1:**

```
// Java program to demonstrate the plusDays() method

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

        // Subtracts the number of days
        System.out.println("Date1 after adding days: "
 + date1.plusDays(-120));
    }
}
```

**输出:**

```
Date1: 2018-12-12T13:30:30+05:00
Date1 after adding days: 2018-08-14T13:30:30+05:00

```

**程序二** :

```
// Java program to demonstrate the plusDays() method

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

        // Subtracts the number of days
        System.out.println("Date1 after adding days: " 
+ date1.plusDays(140));
    }
}
```

**输出:**

```
Date1: 2018-12-12T13:30:30+05:00
Date1 after adding days: 2019-05-01T13:30:30+05:00

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # plusDays(长)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#plusDays(long))