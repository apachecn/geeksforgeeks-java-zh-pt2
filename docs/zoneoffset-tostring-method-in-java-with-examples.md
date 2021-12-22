# Java 中的 ZoneOffset toString()方法，示例

> 原文:[https://www . geesforgeks . org/zone offset-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneoffset-tostring-method-in-java-with-examples/)

**java.time 包**中 **ZoneOffset 类**的 **toString()** 方法用于获取 ZoneOffset 这个实例的字符串表示。此方法不接受任何参数，并返回一个字符串值。这是字符串表示形式。

**语法:**

```java
public static String toString()

```

**参数:**此方法接受不接受任何参数。

**返回值:**这个方法返回一个**字符串值**，这是这个区域偏移实例的字符串表示。

以下示例说明了 ZoneOffset.toString()方法:

**例 1:**

```java
// Java code to illustrate toString() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ZoneOffset
        ZoneOffset zoneOffset
            = ZoneOffset.ofHours(5);

        System.out.println(zoneOffset);

        // Using toString() method
        String string = zoneOffset.toString();

        System.out.println("ZoneOffset string: "
 + string);
    }
}
```

**输出:**

```java
+05:00
ZoneOffset string: +05:00

```

**例 2:**

```java
// Java code to illustrate toString() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ZoneOffset
        ZoneOffset zoneOffset
            = ZoneOffset.of("Z");

        System.out.println(zoneOffset);

        // Using toString() method
        String string = zoneOffset.toString();

        System.out.println("ZoneOffset string: " + string);
    }
}
```

**输出:**

```java
Z
ZoneOffset string: Z

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/ZoneOffset.html#toString--)