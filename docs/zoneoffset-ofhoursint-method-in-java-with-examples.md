# Java 中 hour(int)方法的区域偏移量，示例

> 原文:[https://www . geesforgeks . org/zone offset-of hoursint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneoffset-ofhoursint-method-in-java-with-examples/)

在 **java.time 包**中 **ZoneOffset 类**的**of hour(int)**方法用于获取 ZoneOffset 的实例，使用以小时为单位传递的偏移量作为参数。该方法将小时作为 int 形式的参数，并将其转换为 ZoneOffset。支持的最大范围是从+18:00 到-18:00(含)。

**语法:**

```java
public static ZoneOffset ofHours(int hours)

```

**参数:**该方法接受一个参数**小时**，该参数是要转换为区域偏移实例的整数。

**返回值:**该方法返回从指定小时解析的**区域偏移实例**。

**异常:**如果小时数无效，该方法抛出**日期时间异常**。

以下示例说明了 ZoneOffset.ofHours()方法:

**例 1:**

```java
// Java code to illustrate ofHours() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the hours
        int hours = 10;

        // ZoneOffset using ofHours() method
        ZoneOffset zoneOffset
            = ZoneOffset.ofHours(hours);

        System.out.println(zoneOffset);
    }
}
```

**输出:**

```java
+10:00

```

**示例 2:** 演示日期时间异常

```java
// Java code to illustrate ofHours() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the invalid hours
        int hours = 20;

        try {
            // ZoneOffset using ofHours() method
            ZoneOffset zoneOffset
                = ZoneOffset.ofHours(hours);
        }

        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
java.time.DateTimeException: Zone offset hours not in valid range: value 20 is not in the range -18 to 18

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/ZoneOffset.html#ofHours-int-)