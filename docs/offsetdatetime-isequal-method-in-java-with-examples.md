# Java 中的 OffsetDateTime isEqual()方法，带示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-isequal-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-isequal-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **isEqual()** 方法检查这个日期是否等于指定的日期时间，如果等于则返回 true。

**语法:**

```
public boolean isEqual(OffsetDateTime other)

```

**参数:**该方法接受单个参数**其他**，检查该日期时间是否等于另一个日期时间。

**返回值:**如果等于另一个日期时间，则返回真，否则返回假。

以下程序说明了 *isEqual()* 方法:

**程序 1:**

```
// Java program to demonstrate the isEqual() method

import java.time.OffsetDateTime;
import java.time.ZonedDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the date1
        OffsetDateTime date1
            = OffsetDateTime
                  .parse("2018-12-12T13:30:30+05:00");

        // Parses the date2
        OffsetDateTime date2
            = OffsetDateTime
                  .parse("2018-12-12T13:30:30+05:00");

        // Prints both dates
        System.out.println("Date1: " + date1);
        System.out.println("Date2: " + date2);

        // Compare both
        System.out.println("Date1 equals Date2? "
                           + date1.isEqual(date2));
    }
}
```

**输出:**

```
Date1: 2018-12-12T13:30:30+05:00
Date2: 2018-12-12T13:30:30+05:00
Date1 equals Date2? true

```

**程序二** :

```
// Java program to demonstrate the isEqual() method

import java.time.OffsetDateTime;
import java.time.ZonedDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the date1
        OffsetDateTime date1
            = OffsetDateTime
                  .parse("2018-12-12T13:30:30+05:00");

        // Parses the date2
        OffsetDateTime date2
            = OffsetDateTime
                  .parse("2015-12-12T13:30:30+05:00");

        // Prints both dates
        System.out.println("Date1: " + date1);
        System.out.println("Date2: " + date2);

        // Compare both
        System.out.println("Date1 equals Date2? "
                           + date1.isEqual(date2));
    }
}
```

**输出:**

```
Date1: 2018-12-12T13:30:30+05:00
Date2: 2015-12-12T13:30:30+05:00
Date1 equals Date2? false

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/offsetdatetime . html # isEqual(Java . time . offsetdatetime)](https://docs.oracle.com/javase/10/docs/api/java/time/OffsetDateTime.html#isEqual(java.time.OffsetDateTime))