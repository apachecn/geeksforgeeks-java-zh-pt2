# Java 中的 TimeZone getOffset()方法，示例

> 原文:[https://www . geesforgeks . org/time zone-getoffset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timezone-getoffset-method-in-java-with-examples/)

Java 中**时区类**的 **getOffset()** 方法是用来知道这个时区在某一特定日期从世界协调时或世界协调时的偏移值。

**语法:**

```
public int getOffset(long in_date)
```

**参数:**该方法接受一个参数，**长型**的 **in_date** ，该参数是指自 1970 年 1 月 1 日 00:00:00 格林尼治标准时间以来以毫秒为单位表示的实际日期。

**返回值:**该方法返回时区的**标识。**

下面的程序说明了时区的 getOffset()方法的工作:
**例 1:**

```
// Java code to illustrate getOffset() method

import java.util.*;

public class TimeZoneDemo {
    public static void main(String args[])
    {

        // Creating a TimeZone
        TimeZone offtime_zone
            = TimeZone.getTimeZone("Europe/Rome");

        // Checking the offset for the systems date
        System.out.println("The Offset Value is:"
                           + offtime_zone
                                 .getOffset(Calendar.ZONE_OFFSET));
    }
}
```

**Output:**

```
The Offset Value is:3600000

```

**例 2:**

```
// Java code to illustrate getOffset() method

import java.util.*;

public class TimeZoneDemo {
    public static void main(String args[])
    {

        // Creating a TimeZone
        TimeZone offtime_zone
            = TimeZone.getTimeZone("Pacific/Pago_Pago");

        // Checking the offset for the systems date
        System.out.println("The Offset Value is:"
                           + offtime_zone
                                 .getOffset(Calendar.ZONE_OFFSET));
    }
}
```

**Output:**

```
The Offset Value is:-39600000

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/time zone . html # getOffset()](https://docs.oracle.com/javase/7/docs/api/java/util/TimeZone.html#getDSTSavings())