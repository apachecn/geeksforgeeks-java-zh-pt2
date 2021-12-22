# Java 中的 ZoneId 归一化()方法，示例

> 原文:[https://www . geesforgeks . org/zoneid-normalized-in-Java-method-with-examples/](https://www.geeksforgeeks.org/zoneid-normalized-method-in-java-with-examples/)

Java 中 **ZoneId** 类的 **normalized()** 方法用于对时区 Id 进行规范化，并在可能的情况下返回 ZoneOffset。

该方法返回一个规范化的区域标识，可以用来代替这个标识。规范化过程检查该区域标识的规则是否有固定的偏移量。如果区域标识具有固定偏移量，则返回等于该偏移量的区域偏移量。否则，将返回此。

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
// ZoneId.normalized() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ZoneId object
        ZoneId zoneId
            = ZoneId.of("Europe/Paris");

        // get and print normalised zoneId
        System.out.println("Normalised zoneId: "
                           + zoneId.normalized());
    }
}
```

**Output:**

```
Normalised zoneId: Europe/Paris

```

**程序 2:**

```
// Java program to demonstrate
// ZoneId.normalized() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ZoneId object
        ZoneId zoneId
            = ZoneId.of("Asia/Calcutta");

        // get and print Id
        System.out.println("Normalised zoneId: "
                           + zoneId.normalized());
    }
}
```

**Output:**

```
Normalised zoneId: Asia/Calcutta

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneid . html # normalized()](https://docs.oracle.com/javase/10/docs/api/java/time/ZoneId.html#normalized())