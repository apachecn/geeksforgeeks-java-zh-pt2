# Java 中的 OffsetTime getNano()方法，并附有示例

> 原文:[https://www . geesforgeks . org/offsettime-getnano-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-getnano-method-in-java-with-examples/)

Java 中 OffsetTime 类的 **getNano()** 方法用于从这个时间实例中获取 nano-of-second 字段的值。

**语法:**

```java
public int getNano()

```

**参数:**该方法接受不接受任何参数。

**返回值:**返回从 0 到 999，999，999 的纳米秒。

以下程序说明了 *getNano()* 方法:

**程序 1 :**

```java
// Java program to demonstrate the getNano() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the time
        OffsetTime time = OffsetTime.parse("15:10:30+07:00");

        // gets the nano of second in time
        System.out.println("nano-second: " + time.getNano());
    }
}
```

**输出:**

```java
nano-second: 0

```

**程序二** :

```java
// Java program to demonstrate the getNano() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the time
        OffsetTime time = OffsetTime.parse("11:30:30+06:00");

        // gets nano of second in the time
        System.out.println("Nano-second: " + time.getNano());
    }
}
```

**输出:**

```java
Nano-second: 0

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # getNano–](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#getNano--)