# Java 中的 OffsetDateTime plusSeconds()方法，带示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-plus seconds-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-plusseconds-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **plusSeconds()** 方法返回这个 OffsetDateTime 的一个副本，指定的秒数被添加到解析的日期和时间中。

**语法:**

```java
public OffsetDateTime plusSeconds(long seconds)

```

**参数:**该方法接受单个参数**秒**，该参数指定要添加到解析日期的秒。它也可以是负的，在这种情况下，它会减去秒数。

**返回值:**根据这个日期时间返回一个偏置日期时间，加上秒，不为空。

**异常**:超出支持的数据和时间范围，程序抛出**日期时间异常**。

以下程序说明了 *plusSeconds()* 方法:

**程序 1:**

```java
// Java program to demonstrate the plusSeconds() method

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

        // Subtracts the number of seconds
        System.out.println("Date1 after adding seconds: "
                           + date1.plusSeconds(-120));
    }
}
```

**输出:**

```java
Date1: 2018-12-12T13:30:30+05:00
Date1 after adding seconds: 2018-12-12T13:28:30+05:00

```

**程序二:**

```java
// Java program to demonstrate the plusSeconds() method

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

        // Subtracts the number of seconds
        System.out.println("Date1 after adding seconds: "
                           + date1.plusSeconds(140));
    }
}
```

**输出:**

```java
Date1: 2018-12-12T13:30:30+05:00
Date1 after adding seconds: 2018-12-12T13:32:50+05:00

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # plus seconds(长)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#plusSeconds(long))