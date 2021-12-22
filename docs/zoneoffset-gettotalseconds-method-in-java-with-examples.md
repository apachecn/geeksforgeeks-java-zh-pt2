# Java 中的 ZoneOffset getTotalSeconds()方法，示例

> 原文:[https://www . geesforgeks . org/zone offset-gettotalseconds-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneoffset-gettotalseconds-method-in-java-with-examples/)

**java.time 包**中 **ZoneOffset 类**的 **getTotalSeconds()** 方法用于获取 ZoneOffset 实例中的总秒数。此方法不接受任何参数，并返回一个 int 值。这是总秒数。

**语法:**

```java
public static int getTotalSeconds()

```

**参数:**此方法接受不接受任何参数。

**返回值:**这个方法返回一个**整数值**，这是这个 ZoneOffset 实例的秒数。

以下示例说明了 ZoneOffset.getTotalSeconds()方法:

**例 1:**

```java
// Java code to illustrate getTotalSeconds() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ZoneOffset
        ZoneOffset zoneOffset
            = ZoneOffset.ofHours(5);

        System.out.println(zoneOffset);

        // Using getTotalSeconds() method
        int totalSeconds
 = zoneOffset.getTotalSeconds();

        System.out.println("Total seconds: " 
+ totalSeconds);
    }
}
```

**输出:**

```java
+05:00
Total seconds: 18000

```

**例 2:**

```java
// Java code to illustrate getTotalSeconds() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ZoneOffset
        ZoneOffset zoneOffset
            = ZoneOffset.of("Z");

        System.out.println(zoneOffset);

        // Using getTotalSeconds() method
        int totalSeconds
 = zoneOffset.getTotalSeconds();

        System.out.println("Total seconds: "
 + totalSeconds);
    }
}
```

**输出:**

```java
Z
Total seconds: 0

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/ZoneOffset.html#getTotalSeconds--)