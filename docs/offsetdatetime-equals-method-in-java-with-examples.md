# Java 中的 OffsetDateTime equals()方法，示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-equals-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **equals()** 方法检查这个日期时间是否等于另一个日期时间。
**语法:**

```
public boolean equals(Object obj)
```

**参数:**该方法接受单个参数**其他**，检查该日期时间是否等于另一个日期时间。
**返回值:**如果等于另一个日期时间，则返回真，否则返回假。
以下程序说明了*等于()*方法:
**程序 1 :**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the equals() method

import java.time.OffsetDateTime;
import java.time.ZonedDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the date1
        OffsetDateTime date1 = OffsetDateTime.parse("2018-12-12T13:30:30+05:00");

        // Parses the date2
        OffsetDateTime date2 = OffsetDateTime.parse("2018-12-12T13:30:30+05:00");

        // Prints both dates
        System.out.println("Date1: " + date1);
        System.out.println("Date2: " + date2);

        // Compare both
        System.out.println("On comparing we get " + date1.equals(date2));
    }
}
```

**Output**

```
Date1: 2018-12-12T13:30:30+05:00
Date2: 2018-12-12T13:30:30+05:00
On comparing we get true
```

**节目 2** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the equals() method
import java.time.OffsetDateTime;
import java.time.ZonedDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the date1
        OffsetDateTime date1 = OffsetDateTime.parse("2018-12-12T13:30:30+05:00");

        // Parses the date2
        OffsetDateTime date2 = OffsetDateTime.parse("2015-12-12T13:30:30+05:00");

        // Prints both dates
        System.out.println("Date1: " + date1);
        System.out.println("Date2: " + date2);

        // Compare both
        System.out.println("On comparing we get " + date1.equals(date2));
    }
}
```

**Output**

```
Date1: 2018-12-12T13:30:30+05:00
Date2: 2015-12-12T13:30:30+05:00
On comparing we get false
```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsetdatetime . html # equals-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetDateTime.html#equals-java.lang.Object-)