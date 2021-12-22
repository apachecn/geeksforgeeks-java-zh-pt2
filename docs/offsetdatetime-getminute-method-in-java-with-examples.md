# Java 中的 OffsetDateTime getMinute()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsetdatetime-get minute-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-getminute-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **getMinute()** 方法获取小时分钟字段。

**语法:**

```java
public int getMinute()

```

**参数:**此方法接受不接受任何参数。

**返回值:**返回 0 到 59 之间的分钟数。
下面的程序说明了 *getMinute()* 方法:

**程序 1 :**

```java
// Java program to demonstrate the getMinute() method

import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2018-12-03T12:30:30+01:00");

        // Prints the minute of given date
        System.out.println("Minute: " + date.getMinute());
    }
}
```

**Output:**

```java
Minute: 30

```

**程序 2** :

```java
// Java program to demonstrate the getMinute() method
import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2016-12-31T12:30:30+05:00");

        // Prints the minute of given date
        System.out.println("Minute: " + date.getMinute());
    }
}
```

**Output:**

```java
Minute: 30

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsetdatetime . html # getMinute–](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetDateTime.html#getMinute--)