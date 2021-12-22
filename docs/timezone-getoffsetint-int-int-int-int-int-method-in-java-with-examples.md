# Java 中 TimeZone getOffset(int，int，int，int，int，int)方法示例

> 原文:[https://www . geesforgeks . org/time zone-getoffsetint-int-int-int-int-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timezone-getoffsetint-int-int-int-int-int-method-in-java-with-examples/)

Java 中 **[TimeZone 类](https://www.geeksforgeeks.org/java-util-timezone-class-set-1/)** 的 **getOffset(int era，int yr，int mon，int day，int dayOfWeek，int millisec)** 方法用于从 UTC 或协调世界时知道该时区在特定日期或夏令时修改日期的偏移值。这个偏移值可以相加得到当地时间。

**语法:**

```
public abstract int 
    getOffset(int era, int yr, 
              int mon, int day, 
              int dayOfWeek, int millisec)
```

**参数:**该方法可以取下述参数。

*   **纪元:**此为整数型，指给定日期的纪元。
*   **年:**这是整数类型，指给定日期的年份。
*   **月:**此为整数型，指给定日期的月份。
*   **天:**这是整数类型，指给定日期的月中某一天。
*   **dayOfWeek:** 这是整数类型，指给定日期的星期几。
*   **毫秒:**这是整数类型，指的是标准当地时间的毫秒。

**返回值:**该方法以毫秒为单位返回**偏移量**值，该值可以加入到 GMT 中得到当地时间。

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
                           + offtime_zone.getOffset(
                                 1, 2018, 5, 12, 2, 500));
    }
}
```

**Output:**

```
The Offset Value is:7200000

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
                           + offtime_zone.getOffset(
                                 1, 1995, 9, 20, 2, 700));
    }
}
```

**Output:**

```
The Offset Value is:-39600000

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/time zone . html # getOffset(int，%20int，%20int，%20int，%20int，%20int)](https://docs.oracle.com/javase/7/docs/api/java/util/TimeZone.html#getOffset(int, %20int, %20int, %20int, %20int, %20int))