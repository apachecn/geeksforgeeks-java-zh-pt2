# Java 中的 OffsetDateTime plusDays()方法，带示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-plus days-method-in-Java-with-examples-2/](https://www.geeksforgeeks.org/offsetdatetime-plusdays-method-in-java-with-examples-2/)

Java 中 OffsetDateTime 类的 **plusHours()** 方法返回这个 OffsetDateTime 的一个副本，指定的小时数被添加到解析的日期和时间中。

**语法:**

```java
public OffsetDateTime plusHours(long hours)

```

**参数:**该方法接受单个参数**小时数**，该参数指定要添加到解析日期的小时数。它也可以是负的，在这种情况下，它会减去小时数。

**返回值:**根据这个日期时间返回一个偏置日期时间，加上小时，不为空。

**异常**:超出支持的数据和时间范围，程序抛出**日期时间异常**。

以下程序说明了*plus shours()*方法:

**程序 1:**

```java
// Java program to demonstrate the plusHours() method

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

        // Subtracts the number of hours
        System.out.println("Date1 after adding hours: "
                           + date1.plusHours(-120));
    }
}
```

**输出:**

```java
Date1: 2018-12-12T13:30:30+05:00
Date1 after adding hours: 2018-12-07T13:30:30+05:00

```

**程序二** :

```java
// Java program to demonstrate the plusHours() method

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

        // Subtracts the number of hours
        System.out.println("Date1 after adding hours: "
                           + date1.plusHours(140));
    }
}
```

**输出:**

```java
Date1: 2018-12-12T13:30:30+05:00
Date1 after adding hours: 2018-12-18T09:30:30+05:00

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # plusHours(长)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#plusHours(long))