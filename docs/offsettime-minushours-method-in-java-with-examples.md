# Java 中的 OffsetTime minusHours()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsettime-minoshours-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-minushours-method-in-java-with-examples/)

Java 中 OffsetTime 类的 **minusHours()** 方法返回这个 OffsetTime 的一个副本，参数中的指定小时被减去。

**语法:**

```java
public OffsetTime minusHours(long hours)

```

**参数:**该方法接受单个参数**小时数**，该参数是要减去的小时数。可能是负面的。

**返回值:**根据这个时间减去小时数返回一个偏移量，不为空。

下面的程序说明了 minusHours()方法:

**程序 1 :**

```java
// Java program to demonstrate the minusHours() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {
        // Parses the time
        OffsetTime time = OffsetTime.parse("11:10:10+05:05");

        // Specified hours subtracted
        System.out.println("After subtraction, time is: " 
                                      + time.minusHours(5));
    }
}
```

**输出:**

```java
After subtraction, time is: 06:10:10+05:05

```

**程序二** :

```java
// Java program to demonstrate the minusHours() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {
        // Parses the time
        OffsetTime time = OffsetTime.parse("11:10:10+05:05");

        // Specified hours subtracted
        System.out.println("After subtraction, time is: " 
                                    + time.minusHours(-5));
    }
}
```

**输出:**

```java
After subtraction, time is: 16:10:10+05:05

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # minoshours-long-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#minusHours-long-)