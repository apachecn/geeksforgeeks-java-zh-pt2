# Java 中的 ZonedDateTime getMonthValue()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-getmonthvvalue-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-getmonthvalue-method-in-java-with-examples/)

一个**区域数据时间**类的**getmonthvvalue()**方法用于从这个区域数据时间中获取 1 到 12 之间的年月字段。

**语法:**

```java
public int getMonthValue()

```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回一个表示一年中月份的**整数**，从 1 到 12。

下面的程序说明了 getMonthValue()方法:

**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.getMonthValue() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // get month field
        int value = zoneddatetime.getMonthValue();

        // print result
        System.out.println("month:" + value);
    }
}
```

**输出:**

```java
month:12

```

**程序二:**

```java
// Java program to demonstrate
// ZonedDateTime.getMonthValue() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-10-25T23:12:38.543+02:00[Europe/Paris]");

        // get month field
        int value = zoneddatetime.getMonthValue();

        // print result
        System.out.println("month:" + value);
    }
}
```

**输出:**

```java
month:10

```

**参考:**[https://docs . Oracle . com/javae/10/docs/API/Java/time/zoneddatetime . html # getmonthvalue()](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#getMonthValue())