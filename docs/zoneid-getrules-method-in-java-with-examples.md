# Java 中的 ZoneId getRules()方法，带示例

> 原文:[https://www . geesforgeks . org/zoneid-getrules-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneid-getrules-method-in-java-with-examples/)

Java 中 **ZoneId** 类的 **getRules()** 方法用于获取该 Id 的时区规则，从而允许执行计算。这些规则提供了与时区相关联的功能，例如给定时刻或本地日期时间的偏移量。这些规则由区域规则提供程序提供。高级提供程序可以支持对规则的动态更新，而无需重新启动 Java 运行时。如果是这样，那么这个方法的结果可能会随着时间的推移而改变。每个单独的调用仍然保持线程安全。

**语法:**

```
public abstract ZoneRules getRules()

```

**参数:**此方法不接受任何内容。

**返回值:**此方法返回规则。

下面的程序说明了 getRules()方法:
**程序 1:**

```
// Java program to demonstrate
// ZoneId.getRules() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ZoneId object
        ZoneId zoneId
            = ZoneId.of("Europe/Paris");

        // get and print rules
        System.out.println("Rules: "
                           + zoneId.getRules());
    }
}
```

**Output:**

```
Rules: ZoneRules[currentStandardOffset=+01:00]

```

**程序 2:**

```
// Java program to demonstrate
// ZoneId.getRules() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ZoneId object
        ZoneId zoneId
            = ZoneId.of("Asia/Calcutta");

        // get and print rules
        System.out.println("Rules: "
                           + zoneId.getRules());
    }
}
```

**Output:**

```
Rules: ZoneRules[currentStandardOffset=+05:30]

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneid . html # getRules()](https://docs.oracle.com/javase/10/docs/api/java/time/ZoneId.html#getRules())