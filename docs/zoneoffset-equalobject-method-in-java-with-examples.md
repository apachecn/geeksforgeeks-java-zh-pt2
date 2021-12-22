# Java 中的 ZoneOffset equal(Object)方法，示例

> 原文:[https://www . geesforgeks . org/zone offset-equal object-in-Java-method-with-examples/](https://www.geeksforgeeks.org/zoneoffset-equalobject-method-in-java-with-examples/)

**java.time 包**中 **ZoneOffset 类**的 **equals(Object)** 方法用于检查作为参数传递给该 ZoneOffset 实例的 ZoneOffset 的另一个实例是否相等。此方法返回一个表示相同内容的布尔值。

**语法:**

```
public boolean equals(Object object)

```

**参数:**这个方法接受一个参数**对象**，它等于这个区域偏移实例。

**返回值:**该方法返回一个**布尔值**，说明该区域偏移量是否等于作为参数传递的实例。

以下示例说明了 ZoneOffset.equals()方法:

**例 1:**

```
// Java code to illustrate equals() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ZoneOffset instance
        ZoneOffset zoneOffset1
            = ZoneOffset.ofHours(5);
        System.out.println("ZoneOffset 1: "
                           + zoneOffset1);

        // Get the ZoneOffset instance
        ZoneOffset zoneOffset2
            = ZoneOffset.ofHours(5);
        System.out.println("ZoneOffset 2: "
                           + zoneOffset2);

        // Using equals() method
        System.out.println("ZoneOffset 1 "
                           + "is equal to ZoneOffset 2: "
                           + zoneOffset1.equals(zoneOffset2));
    }
}
```

**输出:**

```
ZoneOffset 1: +05:00
ZoneOffset 2: +05:00
ZoneOffset 1 is equal to ZoneOffset 2: true

```

**例 2:**

```
// Java code to illustrate equals() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ZoneOffset instance
        ZoneOffset zoneOffset1
            = ZoneOffset.ofHours(5);
        System.out.println("ZoneOffset 1: "
                           + zoneOffset1);

        // Get the ZoneOffset instance
        ZoneOffset zoneOffset3
            = ZoneOffset.ofHours(3);
        System.out.println("ZoneOffset 3: "
                           + zoneOffset3);

        // Using equals() method
        System.out.println("ZoneOffset 1 "
                           + "is equal to ZoneOffset 3: "
                           + zoneOffset1.equals(zoneOffset3));
    }
}
```

**输出:**

```
ZoneOffset 1: +05:00
ZoneOffset 3: +03:00
ZoneOffset 1 is equal to ZoneOffset 3: false

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/ZoneOffset.html#equals-java.lang.Object-)