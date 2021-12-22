# Java 中的 ZonedDateTime getDayOfYear()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-getdayofyear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-getdayofyear-method-in-java-with-examples/)

一个**分区时间**类的**getdayofyeear()**方法用于从这个分区时间中获取一年中的某一天字段。此方法返回从 1 到 365 的整数值，或者闰年为 366。

**语法:**

```java
public int getDayOfYear()

```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回一个**整数**，代表一年中的某一天，从 1 到 365，或者闰年是 366。

下面的程序说明了 getDayOfYear()方法:

**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.getDayOfYear() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // get day-of-year field
        int value = zoneddatetime.getDayOfYear();

        // print result
        System.out.println("day-of-year: " + value);
    }
}
```

**输出:**

```java
day-of-year: 340

```

**程序二:**

```java
// Java program to demonstrate
// ZonedDateTime.getDayOfYear() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        // get day-of-year field
        int value = zoneddatetime.getDayOfYear();

        // print result
        System.out.println("day-of-year: " + value);
    }
}
```

**输出:**

```java
day-of-year: 298

```

**参考:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # getDayOfYear()