# Java 中的 ZonedDateTime getDayOfWeek()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-getdayofweek-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-getdayofweek-method-in-java-with-examples/)

一个 **ZonedDateTime** 类的 **getDayOfWeek()** 方法用于从这个 ZonedDateTime 获取星期几字段，它是一个枚举 DayOfWeek。更多信息可从 DayOfWeek 获得。这包括值的文本名称。

**语法:**

```
public DayOfWeek getDayOfWeek()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个代表星期几的枚举 **DayOfWeek** 。

下面的程序说明了 getDayOfWeek()方法:

**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.getDayOfWeek() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // get day-of-week field
        DayOfWeek value = zoneddatetime.getDayOfWeek();

        // print result
        System.out.println("day-of-week:" + value);
    }
}
```

**输出:**

```
day-of-week:THURSDAY

```

**程序二:**

```
// Java program to demonstrate
// ZonedDateTime.getDayOfWeek() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-10-24T23:12:31.123+02:00[Europe/Paris]");

        // get day-of-week field
        DayOfWeek value = zoneddatetime.getDayOfWeek();

        // print result
        System.out.println("day-of-week:" + value);
    }
}
```

**输出:**

```
day-of-week:WEDNESDAY

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # getDayOfWeek()](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#getDayOfWeek())