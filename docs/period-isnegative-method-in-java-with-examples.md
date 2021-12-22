# 句号是 Java 中的 Negative()方法，示例

> 原文:[https://www . geesforgeks . org/period-is negative-method-in-Java-with-examples/](https://www.geeksforgeeks.org/period-isnegative-method-in-java-with-examples/)

Java 中 period 类的 isNegative()方法用于检查 Period 中的 YEAR、MONTH、DAYS 三个值是否为负。

**语法:**

```java
public boolean isNegative()
```

**参数:**该方法不接受任何参数。

**返回值:**如果给定期间的三个值 YEARs、MONTHS、DAYS 中的任何一个为负，则该方法返回 True，否则返回 false。

下面的程序说明了 Java 中的 isNegative()方法:

**程序 1** :

```java
// Java code to show the function isNegative()
// to check whether any of the three given units
// YEAR, MONTH, DAY is negative

import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodDemo {

    // Function to check if any of the three 
    // YEAR, MONTH, DAY is negative
    static void ifNegative(int year, int months, int days)
    {
        Period period = Period.of(year, months, days);
        System.out.println(period.isNegative());
    }

    // Driver Code
    public static void main(String[] args)
    {
        int year = -12;
        int months = 3;
        int days = 31;

        ifNegative(year, months, days);
    }
}
```

**输出:**

```java
true

```

**程序二** :

```java
// Java code to show the function isNegative()
// to check whether any of the three given units
// YEAR, MONTH, DAY is negative

import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodDemo {

    // Function to check if any of the three
    // YEAR, MONTH, DAY is negative
    static void ifNegative(int year, int months, int days)
    {
        Period period = Period.of(year, months, days);
        System.out.println(period.isNegative());
    }

    // Driver Code
    public static void main(String[] args)
    {
        int year = 12;
        int months = 3;
        int days = 31;

        ifNegative(year, months, days);
    }
}
```

**输出:**

```java
false

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/period . html # is negative–](https://docs.oracle.com/javase/8/docs/api/java/time/Period.html#isNegative--)