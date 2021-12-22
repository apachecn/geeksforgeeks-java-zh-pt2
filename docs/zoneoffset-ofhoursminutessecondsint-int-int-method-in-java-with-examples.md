# Java 中 hoursimnutesseconds(int，int，int)方法的区域偏移量，示例

> 原文:[https://www . geeksforgeeks . org/zone offset-of hours sminutessecondsint-int-int-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneoffset-ofhoursminutessecondsint-int-int-method-in-java-with-examples/)

**java.time 包**中 **ZoneOffset 类**的**of Horsimnutesseconds(int，int，int)** 方法用于获取 ZoneOffset 的实例，使用以小时、分钟和秒为单位传递的偏移量作为参数。该方法将小时、分钟和秒作为 int 形式的参数，并将其转换为 ZoneOffset。

**语法:**

```java
public static ZoneOffset
  ofHoursMinutesSeconds(int hours, 
                        int minutes,  
                        int seconds)

```

**参数:**该方法接受 3 个参数:

*   **Hours** : that is, the integer number of hours to be converted into a ZoneOffset instance. Its range is +18 to -18.
*   **Minute** : This is the int minute to be converted into a ZoneOffset instance. Its range is -59 to +59.
*   **second** : this is the int second to be converted into a ZoneOffset instance. The range is -59 to +59.

**返回值:**该方法返回从指定的小时、分钟和秒解析的**区域偏移实例**。

**异常:**如果小时、分、秒无效，此方法抛出**日期时间异常**。

下面的例子说明了 zoneoffset . of hours minutessconds()方法:

**例 1:**

```java
// Java code to illustrate ofHoursMinutesSeconds() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the hours, minutes and seconds
        int hours = 5;
        int minutes = 20;
        int seconds = 50;

        // ZoneOffset using ofHoursMinutesSeconds() method
        ZoneOffset zoneOffset
            = ZoneOffset
                  .ofHoursMinutesSeconds(hours,
                                         minutes,
                                         seconds);

        System.out.println(zoneOffset);
    }
}
```

**输出:**

```java
+05:20:50

```

**示例 2:** 演示日期时间异常

```java
// Java code to illustrate ofHoursMinutesSeconds() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the invalid hours, minutes and seconds
        int hours = 20;
        int minutes = 5;
        int seconds = 0;

        try {
            // ZoneOffset using ofHoursMinutesSeconds() method
            ZoneOffset zoneOffset
                = ZoneOffset
                      .ofHoursMinutesSeconds(hours,
                                             minutes,
                                             seconds);
        }

        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
java.time.DateTimeException:
 Zone offset hours not in valid range:
 value 20 is not in the range -18 to 18

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/ZoneOffset.html#ofHoursMinutesSeconds-int-int-int-)