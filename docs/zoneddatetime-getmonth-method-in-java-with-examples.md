# Java 中的 ZonedDateTime getMonth()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-get month-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-getmonth-method-in-java-with-examples/)

一个**区域数据时间**类的**GetMount()**方法用于使用来自该区域数据时间的月份枚举来获取年中的月份字段。如果需要访问基元 int 值，则枚举提供 int 值。

**语法:**

```java
public Month getMonth()

```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回一个枚举**月**代表一年中的月份。

下面的程序说明了 getMonth()方法:

**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.getMonth() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // get month field
        Month value = zoneddatetime.getMonth();

        // print result
        System.out.println("month:" + value);
    }
}
```

**输出:**

```java
month:DECEMBER

```

**程序二:**

```java
// Java program to demonstrate
// ZonedDateTime.getMonth() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-10-25T23:12:38.543+02:00[Europe/Paris]");

        // get month field
        Month value = zoneddatetime.getMonth();

        // print result
        System.out.println("month:" + value);
    }
}
```

**输出:**

```java
month:OCTOBER

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # getMonth()](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#getMonth())