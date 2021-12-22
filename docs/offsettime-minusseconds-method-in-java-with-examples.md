# Java 中的 offsettimeminseconds()方法，带示例

> 原文:[https://www . geesforgeks . org/offsettime-mins seconds-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-minusseconds-method-in-java-with-examples/)

Java 中 OffsetTime 类的**mins Seconds()**方法返回这个 OffsetTime 的一个副本，参数中指定的 Seconds 被减去。

**语法:**

```java
public OffsetTime minusSeconds(long Seconds)

```

**参数:**该方法接受单个参数**秒**，即要减去的秒。可能是负面的。

**返回值:**根据减去秒数后的时间返回一个偏移量，并且不为空。

下面的程序说明了负秒()方法:

**程序 1 :**

```java
// Java program to demonstrate the minusSeconds() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {
        // Parses the time
        OffsetTime time = OffsetTime.parse("11:10:10+05:05");

        // Specified Seconds subtracted
        System.out.println("After subtraction, time is: " 
                                   + time.minusSeconds(5));
    }
}
```

**输出:**

```java
After subtraction, time is: 11:10:05+05:05

```

**程序二** :

```java
// Java program to demonstrate the minusSeconds() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {
        // Parses the time
        OffsetTime time = OffsetTime.parse("11:10:10+05:05");

        // Specified Seconds subtracted
        System.out.println("After subtraction, time is: " 
                                   + time.minusSeconds(-5));
    }
}
```

**输出:**

```java
After subtraction, time is: 11:10:15+05:05

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # mins seconds-long-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#minusSeconds-long-)