# Java 中的 SimpleTimeZone getOffset()方法，示例

> 原文:[https://www . geesforgeks . org/simple time zone-get offset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpletimezone-getoffset-method-in-java-with-examples/)

在 SimpleTimeZone 类中，根据传递给它的参数，有两种类型的 getOffset()方法。

### getOffset(int era，int year，int month，int day，int dayOfWeek，int millis)

**SimpleTimeZone 类**的 **getOffset()** 方法用于返回本地时间和 UTC 之间的差异，同时考虑原始偏移和夏令时的影响。这个计算是在毫秒内完成的。
**语法:**

```java
public int getOffset(int era,
                     int year,
                     int month,
                     int day,
                     int dayOfWeek,
                     int millis)

```

**参数:**该功能接受 6 个参数:

*   **纪元-** 指定给定日期的纪元。
*   **年份-** 指定给定日期的年份。
*   **月-** 指定给定日期中的月份。
*   **day-** 指定给定日期的月中日期。
*   **dayOfweek-** 指定给定日期的星期几。
*   **毫秒-** 指定标准当地时间的毫秒数。

**返回值:**返回加到 UTC 得到当地时间的时间，单位为毫秒。

**异常:**如果纪元、月、日、日、星期或毫秒参数超出范围，函数将抛出一个异常 **IllegalArgumentException** 。

下面的程序演示了上述功能:

**程序 1:**

```java
// program to demonstrate the
// function java.util.SimpleTimeZone.getOffset()

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create simple time zone object
        SimpleTimeZone obj
            = new SimpleTimeZone(520, "US");

        // get offset on object obj
        int off
            = obj
                  .getOffset(GregorianCalendar.AD,
                             1000,
                             10,
                             2,
                             4,
                             6000);

        // print offset value
        System.out.println("Offset = "
                           + off);
    }
}
```

**Output:**

```java
Offset = 520

```

**程序 2:**

```java
// program to demonstrate the
// function java.util.SimpleTimeZone.getOffset()
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create simple time zone object
        SimpleTimeZone obj
            = new SimpleTimeZone(780, "US");

        // get offset on object obj
        int off
            = obj
                  .getOffset(GregorianCalendar.AD,
                             1000,
                             10,
                             2,
                             4,
                             6000);

        // print offset value
        System.out.println("Offset = "
                           + off);
    }
}
```

**Output:**

```java
Offset = 780

```

### getoffset(长日期)

**简单时区类**的 **getOffset()** 方法用于返回该时区在给定时间相对于世界协调时的偏移量。

**语法:**

```java
public int getOffset(long date)

```

**参数:**该函数接受单个参数**日期**，该参数指定找到时区偏移的时间。

**返回值:**返回加到 UTC 得到当地时间的时间，单位为毫秒。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

**程序 1:**

```java
// program to demonstrate the
// function java.util.SimpleTimeZone.getOffset()
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create simple time zone object
        SimpleTimeZone obj
            = new SimpleTimeZone(520, "India");

        // get offset on object obj
        int off
            = obj
                  .getOffset(Calendar.ZONE_OFFSET);

        // print offset value
        System.out.println("Offset = "
                           + off);
    }
}
```

**Output:**

```java
Offset = 520

```

**程序 2:**

```java
// program to demonstrate the
// function java.util.SimpleTimeZone.getOffset()
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // create simple time zone object
        SimpleTimeZone obj
            = new SimpleTimeZone(600, "India");

        // get offset on object obj
        int off
            = obj
                  .getOffset(Calendar.ZONE_OFFSET);

        // print offset value
        System.out.println("Offset = "
                           + off);
    }
}
```

**Output:**

```java
Offset = 600

```