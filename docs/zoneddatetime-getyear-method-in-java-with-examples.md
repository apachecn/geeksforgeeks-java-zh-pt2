# Java 中的 ZonedDateTime getYear()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-getyear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-getyear-method-in-java-with-examples/)

一个**分区时间**类的 **getYear()** 方法用于从这个分区时间中获取年份字段。此方法返回年的整数值，从最小年到最大年。

**语法:**

```
public int getYear()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个表示年份的**整数**，从 MIN_YEAR 到 MAX_YEAR。

下面的程序说明了 getYear()方法:

**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.getYear() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // get year field
        int value = zoneddatetime.getYear();

        // print result
        System.out.println("year:" + value);
    }
}
```

**输出:**

```
year:2018

```

**程序二:**

```
// Java program to demonstrate
// ZonedDateTime.getYear() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "1918-10-25T23:12:38.543+02:00[Europe/Paris]");

        // get year field
        int value = zoneddatetime.getYear();

        // print result
        System.out.println("year:" + value);
    }
}
```

**输出:**

```
year:1918

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # getYear()](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#getYear())