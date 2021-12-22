# Java 中的 ZonedDateTime getMinute()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-get minute-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-getminute-method-in-java-with-examples/)

一个**分区时间**类的 **getMinute()** 方法用于从这个分区时间中获取分钟字段。此方法返回 0 到 59 分钟的整数值。

**语法:**

```
public int getMinute()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个表示分钟的**整数**，从 0 到 59。

下面的程序说明了 getMinute()方法:

**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.getMinute() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // get minute field
        int value = zoneddatetime.getMinute();

        // print result
        System.out.println("minute:" + value);
    }
}
```

**输出:**

```
minute:21

```

**程序二:**

```
// Java program to demonstrate
// ZonedDateTime.getMinute() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-10-25T23:12:38.543+02:00[Europe/Paris]");

        // get minute field
        int value = zoneddatetime.getMinute();

        // print result
        System.out.println("minute:" + value);
    }
}
```

**输出:**

```
minute:12

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # getMinute()](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#getMinute())