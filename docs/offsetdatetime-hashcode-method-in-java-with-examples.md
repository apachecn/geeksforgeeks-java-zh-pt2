# Java 中的 OffsetDateTime hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-hashcode-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **hashCode()** 方法用来获取这个日期时间实例的哈希代码。

**语法:**

```java
public int hashCode()

```

**参数:**此方法接受不接受任何参数。

**返回值:**返回合适的哈希码。

以下程序说明了 *hashCode()* 方法:

**程序 1 :**

```java
// Java program to demonstrate the hashCode() method

import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2018-12-03T12:30:30+01:00");

        // Prints the hash-code of given date
        System.out.println("hash-code: " + date.hashCode());
    }
}
```

**输出:**

```java
hash-code: 1561872871

```

**程序二** :

```java
// Java program to demonstrate the hashCode() method

import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2016-10-03T12:30:30+01:20");

        // Prints the hash-code of given date
        System.out.println("hash-code: " + date.hashCode());
    }
}
```

**输出:**

```java
hash-code: 1561871543

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsetdatetime . html # hashCode–](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetDateTime.html#hashCode--)