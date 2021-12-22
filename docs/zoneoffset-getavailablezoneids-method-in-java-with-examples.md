# 区域偏移量 getAvailableZoneIds()方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/zone offset-getavailablezoneids-Java 中的方法-示例/](https://www.geeksforgeeks.org/zoneoffset-getavailablezoneids-method-in-java-with-examples/)

**java.time 包**的 **ZoneOffset** 类的 **getAvailableZoneIds()** 方法用于获取一组可用的区域 id。该集合包括所有可用的基于区域的标识。该标识可以传递给(字符串)的，以创建一个区域标识。尽管在典型的应用程序中，区域标识集是固定的，但它会随着时间的推移而增加。

**语法:**

```java
public static Set getAvailableZoneIds()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回**集合**，该集合是区域标识集合的可修改副本。

以下示例说明了 ZoneOffset.getAvailableZoneIds()方法:

**例 1:**

```java
// Java code to illustrate getAvailableZoneIds() method

import java.time.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ZoneOffset instance
        ZoneOffset zoneOffset
            = ZoneOffset.of("+05:30");

        // get available zones
        // using getAvailableZoneIds()
        Set<String> zoneIds
            = zoneOffset.getAvailableZoneIds();

        // print first record
        System.out.println("First ZoneId in list:"
                           + zoneIds.iterator().next());
    }
}
```

**输出:**

```java
First ZoneId in list:Asia/Aden

```

**例 2:**

```java
// Java code to illustrate getAvailableZoneIds() method

import java.time.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ZoneOffset instance
        ZoneOffset zoneOffset
            = ZoneOffset.of("Z");

        // get available zones
        // using getAvailableZoneIds()
        Set<String> zoneIds
            = zoneOffset.getAvailableZoneIds();

        // print first record
        System.out.println("First ZoneId in list:"
                           + zoneIds.iterator().next());
    }
}
```

**输出:**

```java
First ZoneId in list:Asia/Aden

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/10/docs/api/java/time/ZoneId.html#getAvailableZoneIds())