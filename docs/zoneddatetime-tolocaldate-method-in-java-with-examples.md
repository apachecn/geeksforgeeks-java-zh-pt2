# Java 中的 ZonedDateTime toLocalDate()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-tolocaldate-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-tolocaldate-method-in-java-with-examples/)

一个 **ZonedDateTime** 类的 **toLocalDate()** 方法用于返回这个日期时间对象的 LocalDate 部分，其中的年、月、日与这个日期时间相同。

**语法:**

```
public LocalDate toLocalDate()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个**本地日期**，代表该日期时间的日期部分，不为空。

下面的程序说明了 toLocalDate()方法:

**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.toLocalDate() method

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

        // get LocalDate
        LocalDate value = zoneddatetime.toLocalDate();

        // print result
        System.out.println("LocalDate: " + value);
    }
}
```

**输出:**

```
ZonedDateTime: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
LocalDate: 2018-12-06

```

**程序二:**

```
// Java program to demonstrate
// ZonedDateTime.toLocalDate() method

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

        // get LocalDate
        LocalDate value = zoneddatetime.toLocalDate();

        // print result
        System.out.println("LocalDate: " + value);
    }
}
```

**输出:**

```
ZonedDateTime: 2018-10-25T23:12:31.123+02:00[Europe/Paris]
LocalDate: 2018-10-25

```

**参考:**[https://docs . Oracle . com/javae/10/docs/API/Java/time/zoneddatetime . html # tolocaldate()](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#toLocalDate())