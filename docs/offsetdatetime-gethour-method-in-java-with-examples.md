# Java 中的 OffsetDateTime getHour()方法，带示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-get hour-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-gethour-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **getHour()** 方法获取一天中的小时字段。

**语法:**

```
public int getHour() 

```

**参数:**此方法接受不接受任何参数。

**返回值:**返回 0 到 23 之间的小时数。

以下程序说明了 *getHour()* 方法:

**程序 1 :**

```
// Java program to demonstrate the getHour() method

import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2018-12-03T12:30:30+01:00");

        // Prints the hour of given date
        System.out.println("Hour: " + date.getHour());
    }
}
```

**输出:**

```
Hour: 12

```

**程序二** :

```
// Java program to demonstrate the getDayOfYear() method
import java.time.OffsetDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2016-12-31T12:30:30+05:00");

        // Prints the hour of given date
        System.out.println("Hour: " + date.getHour());
    }
}
```

**输出:**

```
Hour: 12

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsetdatetime . html # getHour–](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetDateTime.html#getHour--)