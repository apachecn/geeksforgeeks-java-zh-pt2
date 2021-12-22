# Java 中的 OffsetDateTime getDayOfYear()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsetdatetime-getdayofyear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-getdayofyear-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的**getdayofyeear()**方法获取年月日字段。

**语法:**

```
public int getDayOfYear()

```

**参数:**此方法接受不接受任何参数。

**返回值:**返回一年中的某一天，范围从 1 到 365，如果该年是闰年，则返回 366。

以下程序说明了 *getDayOfMonth()* 方法:

**程序 1 :**

```
// Java program to demonstrate the getDayOfYear() method

import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2018-12-03T12:30:30+01:00");

        // Prints the day of given date in year
        System.out.println("Day in year: " + date.getDayOfYear());
    }
}
```

**输出:**

```
Day in year: 337

```

**程序二** :

```
// Java program to demonstrate the getDayOfYear() method
import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2016-12-31T12:30:30+01:00");

        // Prints the day of given date in year
        System.out.println("Day in year: " + date.getDayOfYear());
    }
}
```

**输出:**

```
Day in year: 366

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsetdatetime . html # getDayOfYear–](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetDateTime.html#getDayOfYear--)