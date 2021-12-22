# 时区 getTimeZone()方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/time zone-gettimezone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timezone-gettimezone-method-in-java-with-examples/)

Java 中**时区类**的 **getTimeZone()** 方法用于知道任何传递的时区标识的实际时区。

**语法:**

```
public static TimeZone getTimeZone(*String the_ID*)
```

**参数:**该方法采用字符串数据类型的一个参数**的 _ID** ，该参数是指需要知道时区的 ID。

**返回值:**该方法返回传递的标识的指定时区，或者如果程序无法理解指定的标识，则返回格林尼治标准时间区域。

下面的程序说明了时区的 getTimeZone()方法的工作:
**示例 1:**

```
// Java code to illustrate getTimeZone() method

import java.util.*;

public class TimeZoneDemo {
    public static void main(String args[])
    {

        // Creating a TimeZone
        TimeZone the_time_zone
            = TimeZone.getDefault();

        // Knowing the TimeZone
        System.out.println("The TimeZone is: "
                           + the_time_zone
                                 .getTimeZone("GMT+5:30"));
    }
}
```

**Output:**

```
The TimeZone is: sun.util.calendar.ZoneInfo[id="GMT+05:30",
offset=19800000, dstSavings=0, useDaylight=false, transitions=0, lastRule=null]

```

**例 2:**

```
// Java code to illustrate getTimeZone() method

import java.util.*;

public class TimeZoneDemo {
    public static void main(String args[])
    {

        // Creating a TimeZone
        TimeZone the_time_zone
            = TimeZone.getDefault();

        // Knowing the TimeZone
        System.out.println("The TimeZone is: "
                           + the_time_zone
                                 .getTimeZone("GMT-3:30"));
    }
}
```

**Output:**

```
The TimeZone is: sun.util.calendar.ZoneInfo[id="GMT-03:30",
offset=-12600000, dstSavings=0, useDaylight=false, transitions=0, lastRule=null]

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/time zone . html # getTimeZone()](https://docs.oracle.com/javase/7/docs/api/java/util/TimeZone.html#getDSTSavings())