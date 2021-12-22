# Java 中的 ZonedDateTime getDayOfMonth()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-getdayofmonth-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-getdayofmonth-method-in-java-with-examples/)

一个**区域日期时间**类的 **getDayOfMonth()** 方法用来从这个区域日期时间中获取月中的日期字段。此方法返回从 1 到 31 的整数值。

**语法:**

```java
public int getDayOfMonth()

```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回一个表示月中某一天的**整数**，从 1 到 31。

下面的程序说明了 getDayOfMonth()方法:

**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.getDayOfMonth() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // get day-of-month field
        int value = zoneddatetime.getDayOfMonth();

        // print result
        System.out.println("day-of-month:" + value);
    }
}
```

**输出:**

```java
day-of-month:6

```

**程序二:**

```java
// Java program to demonstrate
// ZonedDateTime.getDayOfMonth() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        // get day-of-month field
        int value = zoneddatetime.getDayOfMonth();

        // print result
        System.out.println("day-of-month:" + value);
    }
}
```

**输出:**

```java
day-of-month:25

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # getDayOfMonth()](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#getDayOfMonth())