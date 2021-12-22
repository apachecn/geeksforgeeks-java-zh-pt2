# Java 中的 OffsetDateTime plusMinutes()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsetdatetime-plusminutes-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-plusminutes-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **plusMinutes()** 方法返回这个 OffsetDateTime 的一个副本，指定的分钟数被添加到解析的日期和时间中。

**语法:**

```
public OffsetDateTime plusMinutes(long minutes)
```

**参数:**该方法接受单个参数**分钟**，该参数指定要添加到解析日期的分钟数。它也可以是负的，在这种情况下，它会减去分钟数。

**返回值:**根据这个日期时间返回一个 OffsetDateTime，加上分钟，不为空。

**异常**:超出支持的数据和时间范围，程序抛出**日期时间异常**。

以下程序说明了 *plusMinutes()* 方法:

**程序 1:**

```
// Java program to demonstrate the plusMinutes() method

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

        // Subtracts the number of minutes
        System.out.println("Date1 after adding minutes: "
 + date1.plusMinutes(-120));
    }
}
```

**输出:**

```
Date1: 2018-12-12T13:30:30+05:00
Date1 after adding minutes: 2018-12-12T11:30:30+05:00

```

**程序二:**

```
// Java program to demonstrate the plusMinutes() method

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

        // Subtracts the number of minutes
        System.out.println("Date1 after adding minutes: " 
+ date1.plusMinutes(140));
    }
}
```

**输出:**

```
Date1: 2018-12-12T13:30:30+05:00
Date1 after adding minutes: 2018-12-12T15:50:30+05:00

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # plusMinutes(长)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#plusMinutes(long))