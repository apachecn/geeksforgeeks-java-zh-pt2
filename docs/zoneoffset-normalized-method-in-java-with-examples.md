# Java 中的 ZoneOffset 归一化()方法，示例

> 原文:[https://www . geesforgeks . org/zone offset-normalized-in-Java-method-with-examples/](https://www.geeksforgeeks.org/zoneoffset-normalized-method-in-java-with-examples/)

Java 中 **ZoneOffset** 类的 **normalized()** 方法用于对时区 ID 进行规范化，并在可能的情况下返回一个 ZoneOffset。

该方法返回一个规范化的区域偏移量，可以用来代替这个标识。规范化过程检查该区域偏移量的规则是否具有固定偏移量。如果区域偏移具有固定偏移，则返回等于该偏移的区域偏移。否则，将返回此。

**语法:**

```
public ZoneId normalized()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回时区唯一标识。

下面的程序说明了归一化()方法:

**程序 1:**

```
// Java program to demonstrate
// ZoneOffset.normalized() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ZoneOffset instance
        ZoneOffset zoneOffset
            = ZoneOffset.of("+05:30");

        // get and print normalised zoneId
        System.out.println("Normalised zoneId: "
                           + zoneOffset.normalized());
    }
}
```

**输出:**

```
Normalised zoneId: +05:30

```

**程序二:**

```
// Java program to demonstrate
// ZoneOffset.normalized() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the ZoneOffset instance
        ZoneOffset zoneOffset
            = ZoneOffset.of("Z");

        // get and print Id
        System.out.println("Normalised zoneId: "
                           + zoneOffset.normalized());
    }
}
```

**输出:**

```
Normalised zoneId: Z

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/10/docs/api/java/time/ZoneId.html#normalized())