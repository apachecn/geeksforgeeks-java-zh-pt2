# Java 中的 ZonedDateTime toLocalDateTime()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-tolocaldatetime-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-tolocaldatetime-method-in-java-with-examples/)

一个 **ZonedDateTime** 类的 **toLocalDateTime()** 方法用于返回这个日期时间对象的 LocalDateTime 部分，其中的年、月、日和时间与这个日期时间相同。

**语法:**

```
public LocalDateTime toLocalDateTime()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个**本地日期时间**，代表该日期时间的本地日期时间部分。

下面的程序说明了 toLocalDateTime()方法:

**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.toLocalDateTime() method

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

        // get LocalDateTime
        LocalDateTime value = zoneddatetime.toLocalDateTime();

        // print result
        System.out.println("LocalDateTime: " + value);
    }
}
```

**输出:**

```
ZonedDateTime: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
LocalDateTime: 2018-12-06T19:21:12.123

```

**程序二:**

```
// Java program to demonstrate
// ZonedDateTime.toLocalDateTime() method

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

        // get LocalDateTime
        LocalDateTime value = zoneddatetime.toLocalDateTime();

        // print result
        System.out.println("LocalDateTime: " + value);
    }
}
```

**输出:**

```
ZonedDateTime :2018-10-25T23:12:31.123+02:00[Europe/Paris]
LocalDateTime: 2018-10-25T23:12:31.123

```

**参考:**[https://docs . Oracle . com/javae/10/docs/API/Java/time/zoneddatetime . html # tolocaldatetime()](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#toLocalDateTime())