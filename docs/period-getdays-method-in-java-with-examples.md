# Java 中的 Period getDays()方法，带示例

> 原文:[https://www . geesforgeks . org/period-getdays-method-in-Java-with-examples/](https://www.geeksforgeeks.org/period-getdays-method-in-java-with-examples/)

Java 中 Period 类的 getDays()方法用于获取当前周期中使用它的天数。

**语法:**

```java
public int getDays()
```

**参数:**该方法不接受任何参数。

**返回值:**该函数返回给定周期内的天数。

下面的程序说明了上述方法:

**程序 1:**

```java
// Java code to show the function getDays()
// to get number of days from given period
import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodDemo {

    // Function to get number of days of given period
    static void getNumberOfDays(int year, int months, int days)
    {
        Period period = Period.of(year, months, days);
        System.out.println(period.getDays());
    }

    // Driver Code
    public static void main(String[] args)
    {

        int year = 8;
        int months = 5;
        int days = 25;

        getNumberOfDays(year, months, days);
    }
}
```

**输出:**

```java
25

```

**程序二:**

```java
// Java code to show the function getDays()
// to get number of days from given period
import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodDemo {

    // Function to get number of days of given period
    static void getNumberOfDays(int year, int months, int days)
    {
        Period period = Period.of(year, months, days);
        System.out.println(period.getDays());
    }

    // Driver Code
    public static void main(String[] args)
    {

        int year = 0;
        int months = 0;
        int days = 365;

        getNumberOfDays(year, months, days);
    }
}
```

**输出:**

```java
365

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/period . html # getDays–](https://docs.oracle.com/javase/8/docs/api/java/time/Period.html#getDays--)