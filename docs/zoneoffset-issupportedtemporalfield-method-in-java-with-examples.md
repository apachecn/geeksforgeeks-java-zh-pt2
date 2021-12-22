# 区域偏移量问题支持 Java 中的(临时字段)方法，示例

> 原文:[https://www . geesforgeks . org/zone offset-issupportedtemporalfield-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneoffset-issupportedtemporalfield-method-in-java-with-examples/)

**java.time 包**中 **ZoneOffset 类**的**isSupported(TemporalField)**方法用于检查作为参数传递的 temporal field 是否受 ZoneOffset 支持。此方法返回一个表示相同内容的布尔值。

**语法:**

```
public boolean isSupported(TemporalField temporalField)

```

**参数:**该方法接受一个参数**临时字段**，如果该区域偏移实例支持该参数，则需要检查该参数。

**返回值:**该方法返回一个**布尔值**，说明该区域偏移实例是否支持该临时字段。

以下示例说明了 ZoneOffset.isSupported()方法:

**例 1:**

```
// Java code to illustrate isSupported() method

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

        // Using isSupported() method
        System.out.println("Is Second supported: "
                           + zoneOffset.isSupported(ChronoField.OFFSET_SECONDS));
    }
}
```

**输出:**

```
ZoneOffset: +05:30
Is Second supported: true

```

**例 2:**

```
// Java code to illustrate isSupported() method

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

        // Using isSupported() method
        System.out.println("Is Nano-Of-The-Day supported: "
                           + zoneOffset.isSupported(ChronoField.NANO_OF_DAY));
    }
}
```

**输出:**

```
ZoneOffset: +05:00
Is Nano-Of-The-Day supported: false

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/ZoneOffset.html#isSupported-java.time.temporal.TemporalField-)