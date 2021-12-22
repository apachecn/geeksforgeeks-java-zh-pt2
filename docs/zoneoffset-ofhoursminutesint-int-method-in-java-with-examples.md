# Java 中 HoursMinutes(int，int)方法的区域偏移量，示例

> 原文:[https://www . geesforgeks . org/zone offset-of hours sminutesint-int-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneoffset-ofhoursminutesint-int-method-in-java-with-examples/)

**java.time 包**中 **ZoneOffset 类**的**of Horsimnutes(int，int)** 方法用于使用作为参数传递的以小时和分钟为单位的偏移量来获取 ZoneOffset 的实例。该方法将小时和分钟作为 int 形式的参数，并将其转换为 ZoneOffset。

**语法:**

```
public static ZoneOffset 
    ofHoursMinutes(int hours, int minutes)

```

**参数:**该方法接受两个参数:

*   **Hours** : that is, the integer number of hours to be converted into a ZoneOffset instance. Its range is +18 to -18.
*   **Minute** : This is an integer to be converted into a ZoneOffset instance. The range is -59 to +59.

**返回值:**该方法返回从指定的小时和分钟解析的**区域偏移实例**。

**异常:**如果小时和分钟无效，该方法抛出**日期时间异常**。

以下示例说明了 ZoneOffset.ofHoursMinutes()方法:

**例 1:**

```
// Java code to illustrate ofHoursMinutes() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the hours and minutes
        int hours = 5;
        int minutes = 20;

        // ZoneOffset using ofHoursMinutes() method
        ZoneOffset zoneOffset
            = ZoneOffset.ofHoursMinutes(hours, minutes);

        System.out.println(zoneOffset);
    }
}
```

**输出:**

```
+05:20

```

=

**示例 2:** 演示日期时间异常

```
// Java code to illustrate ofHoursMinutes() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the invalid hours and minutes
        int hours = 20;
        int minutes = 5;

        try {
            // ZoneOffset using ofHoursMinutes() method
            ZoneOffset zoneOffset
                = ZoneOffset.ofHoursMinutes(hours, minutes);
        }

        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
java.time.DateTimeException:
 Zone offset hours not in valid range:
 value 20 is not in the range -18 to 18

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/ZoneOffset.html#ofHoursMinutes-int-int-)