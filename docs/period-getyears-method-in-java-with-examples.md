# Java 中的 Period getYears()方法，带示例

> 原文:[https://www . geesforgeks . org/period-getyears-method-in-Java-with-examples/](https://www.geeksforgeeks.org/period-getyears-method-in-java-with-examples/)

Java 中的 Period 的 getYears()方法用于获取使用它的这个期间的年数。

**注:** 15 个月不等于 1 年 3 个月。

**语法:**

```
public List getYears()
```

**参数:**该方法不接受任何参数。

**返回:**此方法返回本期的年数。

下面的程序说明了上述方法:

**程序 1** :

```
// Java code to show the function getYears()
// to get the number of years in the period
import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodDemo {

    // Function to get the number of years
    static void getNumberOfDays(int year, int months, int days)
    {
        Period period = Period.of(year, months, days);
        System.out.println(period.getYears());
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

```
12

```

**程序二** :

```
// Java code to show the function getYears()
// to get the number of years in the period
import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodDemo {

    // Function to get the number of years
    static void getNumberOfDays(int year, int months, int days)
    {
        Period period = Period.of(year, months, days);
        System.out.println(period.getYears());
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

```
-12

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/period . html # getYears–](https://docs.oracle.com/javase/8/docs/api/java/time/Period.html#getYears--)