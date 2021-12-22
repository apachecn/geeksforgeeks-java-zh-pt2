# Java 中的 OffsetDateTime getMonth()方法，带示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-get month-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-getmonth-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **getMonth()** 方法使用 Month 枚举获取年月字段。

**语法:**

```java
public Month getMonth()

```

**参数:**此方法接受不接受任何参数。

**返回值:**返回年月日，不为空..

以下程序说明了 *getMonth()* 方法:

**程序 1 :**

```java
// Java program to demonstrate the getMonth() method

import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2018-12-03T12:30:30+01:00");

        // Prints the month of given date
        System.out.println("Month: " + date.getMonth());
    }
}
```

**输出:**

```java
Month: DECEMBER

```

**程序二** :

```java
// Java program to demonstrate the getMonth() method
import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2016-11-31T12:30:30+05:00");

        // Prints the month of given date
        System.out.println("Month: " + date.getMonth());
    }
}
```

**输出:**

```java
Month: NOVEMBER

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsetdatetime . html # getMonth–](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetDateTime.html#getMonth--)