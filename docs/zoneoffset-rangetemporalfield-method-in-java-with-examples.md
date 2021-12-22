# Java 中的区域偏移范围(临时字段)方法，示例

> 原文:[https://www . geesforgeks . org/zone offset-range temporal field-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneoffset-rangetemporalfield-method-in-java-with-examples/)

Java 中的区域偏移量范围(临时字段)方法，示例

**java.time 包**中 **ZoneOffset 类**的 **range(临时字段)**方法用于获取 ZoneOffset 中作为参数传递的临时字段的范围。此方法返回一个值范围值，表示相同。

**语法:**

```java
public ValueRange range(TemporalField temporalField)

```

**参数:**该方法接受一个参数**临时字段**，它是在该区域偏移实例中查询范围的字段。它不应为空。

**返回值:**该方法返回一个**值范围值**，说明该区域偏移实例中该临时字段的范围。

**异常:**此方法抛出:

*   **Date and time exception** : If the range of the field cannot be obtained.
*   不支持的 dtime type exception:唉哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟。

以下示例说明了 ZoneOffset.range()方法:

**例 1:**

```java
// Java code to illustrate range() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ZoneOffset instance
        ZoneOffset zoneOffset
            = ZoneOffset.of("+05:30");
        System.out.println("ZoneOffset: "
                           + zoneOffset);

        // Using range() method
        System.out.println("Second value: "
                           + zoneOffset.range(ChronoField.OFFSET_SECONDS));
    }
}
```

**输出:**

```java
ZoneOffset: +05:30
Second value: -64800 - 64800

```

**示例 2:** 显示不支持的临时异常

```java
// Java code to illustrate range() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        try {
            // Get the ZoneOffset instance
            ZoneOffset zoneOffset
                = ZoneOffset.ofHours(5);
            System.out.println("ZoneOffset: "
                               + zoneOffset);

            // Using range() method
            System.out.println("Second value: "
                               + zoneOffset.range(ChronoField.NANO_OF_DAY));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
ZoneOffset: +05:00
java.time.temporal.UnsupportedTemporalTypeException: Unsupported field: NanoOfDay

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/ZoneOffset.html#range-java.time.temporal.TemporalField-)