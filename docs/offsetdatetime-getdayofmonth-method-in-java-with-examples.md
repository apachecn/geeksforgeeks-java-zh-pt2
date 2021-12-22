# Java 中的 OffsetDateTime getDayOfMonth()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsetdatetime-getdayofmonth-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-getdayofmonth-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **getDayOfMonth()** 方法获取月中的某一天字段。

**语法:**

```java
public int getDayOfMonth()

```

**参数:**此方法接受不接受任何参数。

**返回值:**返回月日，可以是 1 到 31。

以下程序说明了 *getDayOfMonth()* 方法:

**程序 1 :**

```java
// Java program to demonstrate the getDayOfMonth() method

import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2018-12-03T12:30:30+01:00");

        // Prints the day of given date
        System.out.println("Day: " + date.getDayOfMonth());
    }
}
```

**输出:**

```java
Day: 3

```

**程序二** :

```java
// Java program to demonstrate the getDayOfMonth() method
import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2018-12-31T12:30:30+01:00");

        // Prints the day of given date
        System.out.println("Day: " + date.getDayOfMonth());
    }
}
```

**输出:**

```java
Day: 31

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsetdatetime . html # getDayOfMonth–](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetDateTime.html#getDayOfMonth--)