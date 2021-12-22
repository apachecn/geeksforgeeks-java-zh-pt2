# Java 中的 ZonedDateTime getNano()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-getnano-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-getnano-method-in-java-with-examples/)

一个**区域数据时间**类的 **getNano()** 方法用于从该区域数据时间中获取 0 到 999，999，999
之间的纳米秒场。

**语法:**

```
public int getNano()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个表示纳米秒的**整数**，从 0 到 999，999，999。

下面的程序说明了 getNano()方法:

**程序 1:**

```
// Java program to demonstrate
// ZonedDateTime.getNano() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // get nano-of-second field
        int value = zoneddatetime.getNano();

        // print result
        System.out.println("nano-of-second:" + value);
    }
}
```

**Output:**

```
nano-of-second:123000000

```

**程序 2:**

```
// Java program to demonstrate
// ZonedDateTime.getNano() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ZonedDateTime object
        ZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-10-25T23:12:38.543+02:00[Europe/Paris]");

        // get nano-of-second field
        int value = zoneddatetime.getNano();

        // print result
        System.out.println("nano-of-second:" + value);
    }
}
```

**Output:**

```
nano-of-second:543000000

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # getNano()](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#getNano())