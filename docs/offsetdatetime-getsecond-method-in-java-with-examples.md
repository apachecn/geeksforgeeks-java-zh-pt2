# Java 中的 OffsetDateTime getSecond()方法，带示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-get second-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-getsecond-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **getSecond()** 方法用于获取分钟秒字段的值。

**语法:**

```java
public int getSecond()

```

**参数:**此方法接受不接受任何参数。

**返回值:**返回 0 到 59 的分钟秒数。

以下程序说明了 *getSecond()* 方法:

**程序 1 :**

```java
// Java program to demonstrate the getSecond() method

import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2018-12-03T12:30:30+01:00");

        // Prints the second of given date
        System.out.println("second: " + date.getSecond());
    }
}
```

**输出:**

```java
second: 30

```

**程序二** :

```java
// Java program to demonstrate the getSecond() method

import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2016-10-03T12:30:30+01:20");

        // Prints the second of given date
        System.out.println("second: " + date.getSecond());
    }
}
```

**输出:**

```java
second: 30

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsetdatetime . html # getSecond–](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetDateTime.html#getSecond--)