# Java 中的 OffsetDateTime getYear()方法，带示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-getyear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-getyear-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **getYear()** 方法用于获取 Year 字段的值。

**语法:**

```
public int getYear()

```

**参数:**该方法不接受任何参数。

**返回值:**返回年份，从 MIN_YEAR 到 MAX_YEAR。

下面的程序说明了 *getYear()* 方法:

**程序 1 :**

```
// Java program to demonstrate the getYear() method

import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2018-12-03T12:30:30+01:00");

        // Prints the year of given date
        System.out.println("Year: " + date.getYear());
    }
}
```

**输出:**

```
Year: 2018

```

**程序二** :

```
// Java program to demonstrate the getYear() method

import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2016-10-03T12:30:30+01:20");

        // Prints the year of given date
        System.out.println("Year: " + date.getYear());
    }
}
```

**输出:**

```
Year: 2016

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsetdatetime . html # getYear–](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetDateTime.html#getYear--)