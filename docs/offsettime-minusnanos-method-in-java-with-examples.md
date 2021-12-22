# Java 中的 OffsetTime minusNanos()方法，带示例

> 原文:[https://www . geesforgeks . org/offsettime-mins nano-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-minusnanos-method-in-java-with-examples/)

Java 中 OffsetTime 类的**Nanos()**方法返回这个 OffsetTime 的一个副本，参数中指定的 Nanos 被减去。

**语法:**

```
public OffsetTime minusNanos(long Nanos)

```

**参数:**该方法接受单个参数**纳米**，该参数是要减去的纳米。可能是负面的。

**返回值:**根据减去纳米的时间返回一个偏置时间，不为空。

以下程序说明了纳米粒子()方法:

**程序 1 :**

```
// Java program to demonstrate the minusNanos() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {
        // Parses the time
        OffsetTime time = OffsetTime.parse("11:10:10+05:05");

        // Specified Nanos subtracted
        System.out.println("After subtraction, time is: " + time.minusNanos(5));
    }
}
```

**输出:**

```
After subtraction, time is: 11:10:09.999999995+05:05

```

**程序二** :

```
// Java program to demonstrate the minusNanos() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {
        // Parses the time
        OffsetTime time = OffsetTime.parse("11:10:10+05:05");

        // Specified Nanos subtracted
        System.out.println("After subtraction, time is: " + time.minusNanos(-5));
    }
}
```

**输出:**

```
After subtraction, time is: 11:10:10.000000005+05:05

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # mins nanos-long-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#minusNanos-long-)