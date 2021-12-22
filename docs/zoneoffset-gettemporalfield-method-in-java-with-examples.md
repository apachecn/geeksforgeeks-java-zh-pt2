# Java 中的 ZoneOffset get(TemporalField)方法，示例

> 原文:[https://www . geesforgeks . org/zone offset-gettemporalfield-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneoffset-gettemporalfield-method-in-java-with-examples/)

**java.time 包**中 **ZoneOffset 类**的 **get(TemporalField)** 方法用于从这个 ZoneOffset 实例中获取指定的 TemporalField 的值。此方法将临时字段作为参数，并返回该字段的整数值。

**语法:**

```java
public int get(TemporalField temporalField)

```

**参数:**该方法接受一个参数**临时字段**，该参数是该区域偏移实例所必需的。

**返回值:**这个方法返回一个**整数值**，它是作为参数传递给这个 ZoneOffset 实例的临时字段的字段值。

**异常:**如果无法获取字段的值或该值超出字段的有效值范围

*   **This method throws:

    *   **Date and time exception:** If this field is not supported or the value range is beyond int
    *   **, this method throws an exception:** If there is a number overflow** 

以下示例说明了 ZoneOffset.get()方法:

**例 1:**

```java
// Java code to illustrate get() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ZoneOffset instance
        ZoneOffset zoneOffset
            = ZoneOffset.ofHours(5);
        System.out.println("ZoneOffset: "
                           + zoneOffset);

        // Using get() method
        System.out.println("Second value: "
                           + zoneOffset.get(ChronoField.OFFSET_SECONDS));
    }
}
```

**输出:**

```java
ZoneOffset: +05:00
Second value: 18000

```

**示例 2:** 显示日期时间异常

```java
// Java code to illustrate get() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        try {
            // Get the ZoneOffset instance
            ZoneOffset zoneOffset
                = ZoneOffset.ofHours(25);
            System.out.println("ZoneOffset: "
                               + zoneOffset);

            // Using get() method
            System.out.println("Second value: "
                               + zoneOffset.get(ChronoField.OFFSET_SECONDS));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
java.time.DateTimeException: Zone offset hours not in valid range: value 25 is not in the range -18 to 18

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/ZoneOffset.html#get-java.time.temporal.TemporalField-)