# Java 中的 OffsetDateTime compareTo()方法，带示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-compareto-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **compareTo()** 方法将这个日期时间与另一个日期时间进行比较。
**语法:**

```java
public int compareTo(OffsetDateTime other)
```

**参数:**该方法接受单个参数**其他**，指定要比较的其他日期时间，不为空。
**返回值:**返回比较值，少则负，多则正。
以下程序说明了*比较()*方法:
**程序 1 :**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the compareTo() method

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
        System.out.println("On comparing we get " + date1.compareTo(date2));
    }
}
```

**Output**

```java
Date1: 2018-12-12T13:30:30+05:00
Date2: 2018-12-12T13:30:30+05:00
On comparing we get 0
```

**程序 2** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the compareTo() method
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
        System.out.println("On comparing we get " + date1.compareTo(date2));
    }
}
```

**Output**

```java
Date1: 2018-12-12T13:30:30+05:00
Date2: 2015-12-12T13:30:30+05:00
On comparing we get 3
```

**程序 3** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the compareTo() method
import java.time.OffsetDateTime;
import java.time.ZonedDateTime;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the date1
        OffsetDateTime date1 = OffsetDateTime.parse("2013-12-12T13:30:30+05:00");

        // Parses the date2
        OffsetDateTime date2 = OffsetDateTime.parse("2015-12-12T13:30:30+05:00");

        // Prints both dates
        System.out.println("Date1: " + date1);
        System.out.println("Date2: " + date2);

        // Compare both
        System.out.println("On comparing we get " + date1.compareTo(date2));
    }
}
```

**Output**

```java
Date1: 2013-12-12T13:30:30+05:00
Date2: 2015-12-12T13:30:30+05:00
On comparing we get -2
```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/temporal adjuster . html](https://docs.oracle.com/javase/8/docs/api/java/time/temporal/TemporalAdjuster.html)