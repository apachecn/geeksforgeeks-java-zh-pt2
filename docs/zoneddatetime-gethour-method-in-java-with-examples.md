# Java 中的 ZonedDateTime getHour()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-get hour-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-gethour-method-in-java-with-examples/)

一个**区域数据时间**类的 **getHour()** 方法用来从这个区域数据时间中获取一天中的小时字段。此方法返回 0 到 23 之间的整数值。

**语法:**

```
public int getHour()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个表示小时的**整数**，从 0 到 23。

下面的程序说明了 getHour()方法:

**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.getHour() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // get hour field
        int value = zoneddatetime.getHour();

        // print result
        System.out.println("hour: " + value);
    }
}
```

**输出:**

```
hour: 19

```

**程序二:**

```
// Java program to demonstrate
// ZonedDateTime.getHour() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-10-25T23:12:38.543+02:00[Europe/Paris]");

        // get hour field
        int value = zoneddatetime.getHour();

        // print result
        System.out.println("hour: " + value);
    }
}
```

**输出:**

```
hour: 23

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # getHour()](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#getHour())