# Java 中的 OffsetTime atDate()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsettime-at date-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-atdate-method-in-java-with-examples/)

Java 中 OffsetTime 类的 **atDate()** 方法将这个时间和一个日期结合起来，创建一个 OffsetDateTime。

**语法:**

```java
public OffsetDateTime atDate(LocalDate date)

```

**参数:**该方法接受单个参数**日期**，指定要组合的日期，不为空。

**返回值:**返回由该时间和指定日期组成的偏置日期时间，不为空

下面的程序说明了 atDate()方法:

**程序 1 :**

```java
// Java program to demonstrate the atDate() method

import java.time.LocalDate;
import java.time.OffsetDateTime;
import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {
        // parses the current date
        LocalDate date = LocalDate.now();
        System.out.println("Current date: " + date);

        // Parses the current time
        OffsetTime time = OffsetTime.parse("11:10:10+06:03");
        OffsetDateTime datetime = time.atDate(date);
        System.out.println("Current date and time: " + datetime);
    }
}
```

**输出:**

```java
Current date: 2018-12-31
Current date and time: 2018-12-31T11:10:10+06:03

```

**程序二** :

```java
// Java program to demonstrate the atDate() method

import java.time.LocalDate;
import java.time.OffsetDateTime;
import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {
        // parses the current date
        LocalDate date = LocalDate.now();
        System.out.println("Current date: " + date);

        // Parses the current time
        OffsetTime time = OffsetTime.parse("12:15:14+16:03");
        OffsetDateTime datetime = time.atDate(date);
        System.out.println("Current date and time: " + datetime);
    }
}
```

**输出:**

```java
Current date: 2018-12-31
Current date and time: 2018-12-31T12:15:14+16:03

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # at date-Java . time . local date-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#atDate-java.time.LocalDate-)