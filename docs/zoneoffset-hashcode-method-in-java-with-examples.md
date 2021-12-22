# Java 中的 ZoneOffset hashCode()方法，示例

> 原文:[https://www . geesforgeks . org/zone offset-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneoffset-hashcode-method-in-java-with-examples/)

**java.time 包**中 **ZoneOffset 类**的 **hashCode()** 方法用于获取 ZoneOffset 这个实例的 hashCode 值。此方法不接受任何参数，并返回一个 int 值。这是 hashCode 值。

**语法:**

```
public static int hashCode()

```

**参数:**此方法接受不接受任何参数。

**返回值:**这个方法返回一个**整数值**，这是这个 ZoneOffset 实例的哈希值。

以下示例说明了 ZoneOffset.hashCode()方法:

**例 1:**

```
// Java code to illustrate hashCode() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ZoneOffset
        ZoneOffset zoneOffset
            = ZoneOffset.ofHours(5);

        System.out.println(zoneOffset);

        // Using hashCode() method
        int hashCode = zoneOffset.hashCode();

        System.out.println("ZoneOffset hashCode: " 
+ hashCode);
    }
}
```

**输出:**

```
+05:00
ZoneOffset hashCode: 18000

```

**例 2:**

```
// Java code to illustrate hashCode() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ZoneOffset
        ZoneOffset zoneOffset
            = ZoneOffset.of("Z");

        System.out.println(zoneOffset);

        // Using hashCode() method
        int hashCode = zoneOffset.hashCode();

        System.out.println("ZoneOffset hashCode: " 
+ hashCode);
    }
}
```

**输出:**

```
Z
ZoneOffset hashCode: 0

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/ZoneOffset.html#hashCode--)