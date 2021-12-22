# Java 中的 ZonedDateTime toLocalTime()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-to localtime-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-tolocaltime-method-in-java-with-examples/)

一个 **ZonedDateTime** 类的 **toLocalTime()** 方法用于返回这个日期时间对象的 LocalTime 部分，它与这个日期时间具有相同的小时、分钟、秒和纳秒。

**语法:**

```
public LocalTime toLocalTime()

```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回一个**本地时间**代表这个日期时间的时间部分，不为空。

下面的程序说明了 toLocalTime()方法:

**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.toLocalTime() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // print result
        System.out.println("ZonedDateTime: " + zoneddatetime);

        // get LocalTime
        LocalTime value = zoneddatetime.toLocalTime();

        // print result
        System.out.println("LocalTime: " + value);
    }
}
```

**输出:**

```
ZonedDateTime: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
LocalTime: 19:21:12.123

```

**程序二:**

```
// Java program to demonstrate
// ZonedDateTime.toLocalTime() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        // print result
        System.out.println("ZonedDateTime: " + zoneddatetime);

        // get LocalTime
        LocalTime value = zoneddatetime.toLocalTime();

        // print result
        System.out.println("LocalTime: " + value);
    }
}
```

**输出:**

```
ZonedDateTime: 2018-10-25T23:12:31.123+02:00[Europe/Paris]
LocalTime: 23:12:31.123

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # toLocalTime()](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#toLocalTime())