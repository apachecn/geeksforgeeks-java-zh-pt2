# Java 中的 Period get()方法，示例

> 原文:[https://www . geesforgeks . org/period-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/period-get-method-in-java-with-examples/)

Java 中 Period 类的 get()方法用于从这个 Period 获取参数中给出的请求单位(YEARS、MONTHS 或 DAYS)的值。

**语法:**

```java
public long get(TemporalUnit unit)
```

**参数:**该方法接受一个类型为临时单位的单参数*单位*，该单位是获得所需单位的单位。

**返回值:**该函数返回请求单位的长值。

**异常:**

*   **DateTimeException**–如果不支持参数中的单位，此方法将引发 datetime exception。
*   **unsupportedtemporaltypexception**–如果参数中给定的单元不受支持，此方法将引发 unsupportedtemporaltypexception。

下面的程序说明了上述方法:

**程序 1:**

```java
// Java code to show the function get()
// which gives the requested unit
import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodDemo {

    // Function to get requested unit
    static void getUnit(int year, int months, int days)
    {
        Period period = Period.of(year, months, days);
        System.out.println(period.get(ChronoUnit.DAYS));
    }

    // Driver Code
    public static void main(String[] args)
    {

        int year = 8;
        int months = 5;
        int days = 25;

        getUnit(year, months, days);
    }
}
```

**Output:**

```java
25

```

**程序 2:**

```java
// Java code to show the function get()
// which gives the requested unit
import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodDemo {

    // Function to get requested unit
    static void getUnit(int year, int months, int days)
    {
        Period period = Period.of(year, months, days);
        System.out.println(period.get(ChronoUnit.YEARS));
    }

    // Driver Code
    public static void main(String[] args)
    {

        int year = 11;
        int months = 3;
        int days = 21;

        getUnit(year, months, days);
    }
}
```

**Output:**

```java
11

```