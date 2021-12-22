# Java 中的 OffsetTime hashCode()示例

> 原文:[https://www . geesforgeks . org/offsettime-hashcode-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-hashcode-in-java-with-examples/)

Java 中 OffsetTime 类的 **hashCode()** 方法用于获取这个 Time 实例的哈希代码。

**语法:**

```java
public int hashCode()

```

**参数:**该方法接受不接受任何参数。

**返回值:**返回一个合适的哈希码。

以下程序说明了 *hashCode()* 方法:

**程序 1 :**

```java
// Java program to demonstrate the hashCode() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the time
        OffsetTime time = OffsetTime.parse("15:10:30+07:00");

        // gets the hash-code in time
        System.out.println("hash-code: " + time.hashCode());
    }
}
```

**输出:**

```java
hash-code: -1984024609

```

**程序二** :

```java
// Java program to demonstrate the hashCode() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the time
        OffsetTime time = OffsetTime.parse("11:30:30+06:00");

        // gets the hash-code in time
        System.out.println("hash-code: " + time.hashCode());
    }
}
```

**输出:**

```java
hash-code: 745450958

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # hashCode–](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#hashCode--)