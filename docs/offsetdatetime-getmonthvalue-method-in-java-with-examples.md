# Java 中的 OffsetDateTime getMonthValue()方法，带示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-getmonthvvalue-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-getmonthvalue-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的**getmonthvvalue()**方法使用 month 枚举获取年月字段。

**语法:**

```java
public int getMonthValue()

```

**参数:**该方法不接受任何参数。

**返回值:**返回一年中的月份，范围从 1 到 12。

以下程序说明了*getmonthvvalue()*方法:

**节目 1 :**

```java
// Java program to demonstrate the getMonthValue() method

import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2018-12-03T12:30:30+01:00");

        // Prints the month of given date
        System.out.println("Month: " + date.getMonthValue());
    }
}
```

**节目 2** :

```java
// Java program to demonstrate the getMonthValue() method

import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2016-10-03T12:30:30+01:00");

        // Prints the month of given date
        System.out.println("Month: " + date.getMonthValue());
    }
}
```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsetdatetime . html # getmonthvvalue–](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetDateTime.html#getMonthValue--)