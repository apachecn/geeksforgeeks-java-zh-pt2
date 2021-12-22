# Java 中的 Period hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/period-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/period-hashcode-method-in-java-with-examples/)

Java 中 Period 类的 hashCode()方法用来获取这个期间生成的 hashCode。

**语法:**

```java
public int hashCode()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回给定期间生成的 hashCode。

下面的程序说明了 Java 中的 hashCode()方法:

**程序 1** :

```java
// Java code to show the function hashCode()
// to get the hashCode for the given period

import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodDemo {

    // Function to generate hashCode for the given period
    static void getNumberOfDays(int year, int months, int days)
    {
        Period period = Period.of(year, months, days);
        System.out.println(period.hashCode());
    }

    // Driver Code
    public static void main(String[] args)
    {
        int year = 12;
        int months = 3;
        int days = 31;

        getNumberOfDays(year, months, days);
    }
}
```

**输出:**

```java
2032396

```

**程序二** :

```java
// Java code to show the function hashCode()
// to get the hashCode for the given period

import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodDemo {

    // Function to generate hashCode for the given period
    static void getNumberOfDays(int year, int months, int days)
    {
        Period period = Period.of(year, months, days);
        System.out.println(period.hashCode());
    }

    // Driver Code
    public static void main(String[] args)
    {
        int year = -12;
        int months = 3;
        int days = 31;

        getNumberOfDays(year, months, days);
    }
}
```

**输出:**

```java
2032372

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/period . html # hashCode–](https://docs.oracle.com/javase/8/docs/api/java/time/Period.html#hashCode--)