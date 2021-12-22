# Java 中 OffsetTime from()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsettime-from-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-from-method-in-java-with-examples/)

Java 中 OffsetTime 类的 **from()** 方法从一个临时对象中获取 OffsetTime 的一个实例，该实例在方法的参数中传递。

**语法:**

```
public static OffsetTime from(TemporalAccessor temporal)

```

**参数:**该方法接受单个强制参数**时态**，指定要转换的时态对象，不为空。

**返回值:**返回偏移时间，不为空。

以下程序说明了*从()*的方法:

**程序 1 :**

```
// Java program to demonstrate the from() method

import java.time.OffsetTime;
import java.time.ZonedDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // Function called to get current time
        OffsetTime time
            = OffsetTime.from(ZonedDateTime.now());

        // Prints the current time
        System.out.println("Current-time: "
                           + time);
    }
}
```

**输出:**

```
Current-time: 13:07:59.941Z

```

**程序二** :

```
// Java program to demonstrate the from() method

import java.time.OffsetTime;
import java.time.ZonedDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // Function called to get current time
        OffsetTime time
            = OffsetTime.from(ZonedDateTime.now());

        // Prints the current time
        System.out.println("Current-time: "
                           + time);
    }
}
```

**输出:**

```
Current-time: 13:08:03.087Z

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # from-Java . time . temporal accessor-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#from-java.time.temporal.TemporalAccessor-)