# Java 中的 ZonedDateTime toString()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-tostring-method-in-java-with-examples/)

一个**区域数据时间**类的 **toString()** 方法用于将该区域数据时间作为字符串返回。该字符串由本地日期时间后跟区域偏移量组成。如果区域标识与偏移量不同，则输出该标识。

**语法:**

```
public String toString()

```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回这个 ZonedDateTime 实例的**字符串表示**。

下面的程序说明了 toString()方法:

**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.toString() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // print result
        System.out.println("ZonedDateTime: "
                           + zoneddatetime.toString());
    }
}
```

**输出:**

```
ZonedDateTime: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]

```

**程序二:**

```
// Java program to demonstrate
// ZonedDateTime.toString() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-10-25T23:12:31.123+02:00[Europe/Paris]");

        // print result
        System.out.println("ZonedDateTime: "
                           + zoneddatetime.toString());
    }
}
```

**输出:**

```
ZonedDateTime: 2018-10-25T23:12:31.123+02:00[Europe/Paris]

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # toString()](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#toString())