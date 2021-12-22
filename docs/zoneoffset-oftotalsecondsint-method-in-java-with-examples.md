# Java 中的 ZoneOffset ofTotalSeconds(int)方法，示例

> 原文:[https://www . geesforgeks . org/zone offset-of total secondsint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneoffset-oftotalsecondsint-method-in-java-with-examples/)

在 **java.time 包**中 **ZoneOffset 类**的 **ofTotalSeconds(int)** 方法用于使用作为参数传递的以 TotalSeconds 为单位的偏移量来获取 ZoneOffset 的实例。该方法将 totalSeconds 作为 int 形式的参数，并将其转换为 ZoneOffset。

**语法:**

```
public static ZoneOffset
  ofTotalSeconds(int totalSeconds)

```

**参数:**该方法接受一个参数 **totalSeconds** ，该参数将被 int 转换为 ZoneOffset 实例。它的范围是-64800 到+64800。

**返回值:**这个方法返回一个从指定的 totalSeconds 解析而来的 **ZoneOffset 实例**。

**异常:**如果 totalSeconds 无效，该方法抛出**日期时间异常**。

以下示例说明了 ZoneOffset.ofTotalSeconds()方法:

**例 1:**

```
// Java code to illustrate ofTotalSeconds() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the totalSeconds
        int totalSeconds = 5000;

        // ZoneOffset using ofTotalSeconds() method
        ZoneOffset zoneOffset
            = ZoneOffset.ofTotalSeconds(totalSeconds);

        System.out.println(zoneOffset);
    }
}
```

**输出:**

```
+01:23:20

```

**示例 2:** 演示日期时间异常

```
// Java code to illustrate ofTotalSeconds() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the invalid totalSeconds
        int totalSeconds = 100000;

        try {
            // ZoneOffset using ofTotalSeconds() method
            ZoneOffset zoneOffset
                = ZoneOffset.ofTotalSeconds(totalSeconds);
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
 Zone offset not in valid range:
 -18:00 to +18:00

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/ZoneOffset.html#ofTotalSeconds-int-)