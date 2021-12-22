# Java 中的 OffsetDateTime getDayOfWeek()方法，带示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-getdayofweek-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-getdayofweek-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **getDayOfWeek()** 方法获取月中的某一天字段。

**语法:**

```
public int getDayOfMonth()

```

**参数:**此方法接受不接受任何参数。

**返回值:**返回月日，可以是 1 到 31。

以下程序说明了 *getDayOfWeek()* 方法:

**程序 1 :**

```
// Java program to demonstrate the getDayOfWeek() method

import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2018-12-03T12:30:30+01:00");

        // Prints the day of week of given date
        System.out.println("day: " + date.getDayOfWeek());
    }
}
```

**输出:**

```
day: MONDAY

```

**程序二** :

```
// Java program to demonstrate the getDayOfWeek() method

import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2018-12-31T12:30:30+01:00");

        // Prints the day of week of given date
        System.out.println("Day: " + date.getDayOfWeek());
    }
}
```

**输出:**

```
Day: MONDAY

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsetdatetime . html # getDayOfWeek–](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetDateTime.html#getDayOfWeek--)