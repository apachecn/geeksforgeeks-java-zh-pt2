# Java 中的 ZoneOffset getRules()方法，带示例

> 原文:[https://www . geesforgeks . org/zone offset-getrules-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneoffset-getrules-method-in-java-with-examples/)

**java.time 包**中 **ZoneOffset 类**的 **getRules()** 方法用于获取该 ZoneOffset 实例的关联时区规则。此方法获取并返回此区域偏移量实例的区域规则。

**语法:**

```
public ZoneRules getRules()

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回一个**区域规则**，它是与这个区域偏移实例相关联的区域规则。

以下示例说明了 ZoneOffset.getRules()方法:

**例 1:**

```
// Java code to illustrate getRules() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ZoneOffset instance
        ZoneOffset zoneOffset
            = ZoneOffset.of("+05:30");
        System.out.println("ZoneOffset: "
                           + zoneOffset);

        // Using getRules() method
        System.out.println("ZoneRules: "
                           + zoneOffset.getRules());
    }
}
```

**输出:**

```
ZoneOffset: +05:30
ZoneRules: ZoneRules[currentStandardOffset=+05:30]

```

**例 2:**

```
// Java code to illustrate getRules() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ZoneOffset instance
        ZoneOffset zoneOffset
            = ZoneOffset.of("Z");
        System.out.println("ZoneOffset: "
                           + zoneOffset);

        // Using getRules() method
        System.out.println("ZoneRules: "
                           + zoneOffset.getRules());
    }
}
```

**输出:**

```
ZoneOffset: Z
ZoneRules: ZoneRules[currentStandardOffset=Z]

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/ZoneOffset.html#getRules--)