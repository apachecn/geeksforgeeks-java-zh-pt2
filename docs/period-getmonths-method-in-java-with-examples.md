# Java 中的 Period getMonths()方法，带示例

> 原文:[https://www . geesforgeks . org/period-get months-method-in-Java-with-examples/](https://www.geeksforgeeks.org/period-getmonths-method-in-java-with-examples/)

Java 中 Period 类的 getMonths()方法用于获取当前期间中使用它的月数。

**语法:**

```java
public int *getMonths*()
```

**参数:**该方法不接受任何参数。

**返回值:**该函数返回给定期间的月数。

**注:**12 个月和 1 年有区别。

下面的程序说明了上述方法:

**程序 1:**

```java
// Java code to show the function getMonths()
// to get number of months from given period
import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodDemo {

    // Function to get number of months of given period
    static void getNumberOfDays(int year, int months, int days)
    {
        Period period = Period.of(year, months, days);
        System.out.println(period.getMonths());
    }

    // Driver Code
    public static void main(String[] args)
    {

        int year = 0;
        int months = 10;
        int days = 365;

        getNumberOfDays(year, months, days);
    }
}
```

**Output:**

```java
10

```

**程序二**:这不会把 13 个月换算成年。

```java
// Java code to show the function getMonths()
// to get number of months from given period
import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodDemo {

    // Function to get number of months of given period
    static void getNumberOfDays(int year, int months, int days)
    {
        Period period = Period.of(year, months, days);
        System.out.println(period.getMonths());
    }

    // Driver Code
    public static void main(String[] args)
    {

        int year = 1;
        int months = 13;
        int days = 36;

        getNumberOfDays(year, months, days);
    }
}
```

**Output:**

```java
13

```