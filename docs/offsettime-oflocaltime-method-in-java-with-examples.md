# Java 中(LocalTime)方法的偏移量，示例

> 原文:[https://www . geeksforgeeks . org/offsettime-of localtime-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-oflocaltime-method-in-java-with-examples/)

Java 中 **OffsetTime** 类的**(LocalTime，ZoneOffset Offset)** 方法用于根据给定的 local time 和 offset 实例创建 **OffsetTime** 的实例。

**语法:**

```java
public static OffsetTime of(LocalTime time,
                            ZoneOffset offset)

```

**参数:**该方法接受两个参数。

*   **时间**–代表当地时间。它不应为空。
*   **偏移**–表示区域偏移。它不应为空。

**返回值:**该方法返回**偏置时间**。

**异常:**此方法不抛出任何异常。

下面的程序说明了 Java 中 OffsetTime 类的(LocalTime，ZoneOffset)方法:

**程序 1:**

```java
// Java program to demonstrate
// OffsetTime of(
// LocalTime, ZoneOffset) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(
        String[] args)
    {
        // Create OffsetTime object
        OffsetTime offsettime
            = OffsetTime.of(
                LocalTime.now(),
                ZoneOffset.UTC);

        // Print time
        System.out.println(
            "TIME: "
            + offsettime);
    }
}
```

**Output:**

```java
TIME: 03:14:11.212Z

```

**程序 2:**

```java
// Java program to demonstrate
// OffsetTime of(
// LocalTime, ZoneOffset) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(
        String[] args)
    {
        // Create LocalTime object
        LocalTime time
            = LocalTime.of(
                8, 45, 40, 50);

        // Create ZoneOffset object
        ZoneOffset offset
            = ZoneOffset.ofHoursMinutes(
                5, 30);

        // Create OffsetTime object
        OffsetTime offsettime
            = OffsetTime.of(
                time, offset);

        // Print time
        System.out.println(
            "TIME: "
            + offsettime);
    }
}
```

**Output:**

```java
TIME: 08:45:40.000000050+05:30

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsettime . html # of(Java . time . local time，java.time.ZoneOffset)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetTime.html#of(java.time.LocalTime, java.time.ZoneOffset))