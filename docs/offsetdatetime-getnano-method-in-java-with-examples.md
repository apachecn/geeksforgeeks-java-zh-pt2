# Java 中的 OffsetDateTime getNano()方法，带示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-getnano-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-getnano-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **getNano()** 方法得到了 nano-of-second 字段。

**语法:**

```java
public int getNano()

```

**参数:**该方法不接受任何参数。

**返回值:**返回从 0 到 999，999，999 的纳米秒。

以下程序说明了 *getNano()* 方法:

**程序 1 :**

```java
// Java program to demonstrate the getNano() method

import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2018-12-03T12:30:30+01:00");

        // Prints the nano-second of given date
        System.out.println("nano-second: " + date.getNano());
    }
}
```

**输出:**

```java
nano-second: 0

```

**程序二** :

```java
// Java program to demonstrate the getMonthValue() method

import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2016-10-03T12:30:30+01:20");

        // Prints the nano-second of given date
        System.out.println("nano-second: " + date.getNano());
    }
}
```

**输出:**

```java
nano-second: 0

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsetdatetime . html # getNano–](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetDateTime.html#getNano--)