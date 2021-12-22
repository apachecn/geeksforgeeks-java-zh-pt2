# Java 中的 ZonedDateTime getSecond()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-get second-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-getsecond-method-in-java-with-examples/)

一个**区域数据时间**类的 **getSecond()** 方法用于从这个区域数据时间中获取分钟秒字段。此方法返回 0 到 59 之间的第二个整数值。

**语法:**

```
public int getSecond()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个表示分钟秒数的**整数**，从 0 到 59。

下面的程序说明了 getSecond()方法:

**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.getSecond() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // get second-of-minute field
        int value = zoneddatetime.getSecond();

        // print result
        System.out.println("second-of-minute:" + value);
    }
}
```

**输出:**

```
second-of-minute:12

```

**程序二:**

```
// Java program to demonstrate
// ZonedDateTime.getSecond() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-10-25T23:12:38.543+02:00[Europe/Paris]");

        // get second-of-minute field
        int value = zoneddatetime.getSecond();

        // print result
        System.out.println("second-of-minute:" + value);
    }
}
```

**输出:**

```
second-of-minute:38

```

**参考:**[https://docs . Oracle . com/javae/10/docs/API/Java/time/zoneddatetime . html # getsecond()](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#getSecond())