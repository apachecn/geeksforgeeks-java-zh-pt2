# Java 中的 OffsetTime minusMinutes()方法，带示例

> 原文:[https://www . geesforgeks . org/offsettime-mins minutes-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-minusminutes-method-in-java-with-examples/)

Java 中 OffsetTime 类的**Minutes()**方法返回这个 OffsetTime 的一个副本，参数中指定的 Minutes 被减去。

**语法:**

```java
public OffsetTime minusMinutes(long Minutes)

```

**参数:**该方法接受单个参数**分钟**，即要减去的分钟数。可能是负面的。

**返回值:**根据这个时间减去分钟，返回一个偏置时间，不为空。

下面的程序说明了 minusMinutes()方法:

**程序 1 :**

```java
// Java program to demonstrate the minusMinutes() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {
        // Parses the time
        OffsetTime time = OffsetTime.parse("11:10:10+05:05");

        // Specified Minutes subtracted
        System.out.println("After subtraction, time is: "
                                     + time.minusMinutes(5));
    }
}
```

**输出:**

```java
After subtraction, time is: 11:05:10+05:05

```

**程序二** :

```java
// Java program to demonstrate the minusMinutes() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {
        // Parses the time
        OffsetTime time = OffsetTime.parse("11:10:10+05:05");

        // Specified Minutes subtracted
        System.out.println("After subtraction, time is: " 
                                     + time.minusMinutes(-5));
    }
}
```

**输出:**

```java
After subtraction, time is: 11:15:10+05:05

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # mins minutes-long-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#minusMinutes-long-)