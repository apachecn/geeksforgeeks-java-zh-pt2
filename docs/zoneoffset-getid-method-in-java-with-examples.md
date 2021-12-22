# Java 中的 ZoneOffset getId()方法，示例

> 原文:[https://www . geesforgeks . org/zone offset-getid-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneoffset-getid-method-in-java-with-examples/)

**java.time 包**中 **ZoneOffset 类**的 **getId()** 方法用于获取 ZoneOffset 这个实例中的偏移量 Id。此方法不接受任何参数，并返回一个字符串值。这是偏移量标识。

**语法:**

```
public static String getId()

```

**参数:**此方法接受不接受任何参数。

**返回值:**这个方法返回一个**字符串值**，这是这个区域偏移实例的偏移标识。

以下示例说明了 ZoneOffset.getId()方法:

**例 1:**

```
// Java code to illustrate getId() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ZoneOffset
        ZoneOffset zoneOffset
            = ZoneOffset.ofHours(5);

        System.out.println(zoneOffset);

        // Using getId() method
        String id = zoneOffset.getId();

        System.out.println("ZoneOffset ID: " 
+ id);
    }
}
```

**输出:**

```
+05:00
ZoneOffset ID: +05:00

```

**例 2:**

```
// Java code to illustrate getId() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ZoneOffset
        ZoneOffset zoneOffset
            = ZoneOffset.of("Z");

        System.out.println(zoneOffset);

        // Using getId() method
        String id = zoneOffset.getId();

        System.out.println("ZoneOffset ID: " 
+ id);
    }
}
```

**输出:**

```
Z
ZoneOffset ID: Z

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/ZoneOffset.html#getId--)