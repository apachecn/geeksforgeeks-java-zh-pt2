# Java 中的周期归一化()方法，示例

> 原文:[https://www . geesforgeks . org/period-normalized-in-Java-method-with-examples/](https://www.geeksforgeeks.org/period-normalized-method-in-java-with-examples/)

Java 中 Period 类的 normalized()方法用于在规范化年和月之后返回 Period 的新实例。

**语法:**

```java
public Period normalized()
```

**参数:**该功能不接受任何参数。

**返回值:**该函数在对期间的年和月进行归一化后，返回一个 Period 的新实例。

**异常:**它抛出一个**算术异常**。如果发生数字溢出，将捕获此异常。

下面的程序说明了上面的方法:

**程序 1** :

```java
// Java code to show the function to normalize
// months and years of the period
import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodClass {

    // Function to normalize given periods
    static void toNormalize(Period p1)
    {

        System.out.println(p1.normalized());
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Defining period
        int year = 4;
        int months = 15;
        int days = 10;
        Period p1 = Period.of(year, months, days);

        toNormalize(p1);
    }
}
```

**输出:**

```java
P5Y3M10D

```

**程序 2** :这不会使天数正常化。

```java
// Java code to show the function to normalize
// months and years of the period
import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodClass {

    // Function to normalize given periods
    static void toNormalize(Period p1)
    {

        System.out.println(p1.normalized());
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Defining period
        int year = 10;
        int months = 25;
        int days = 366;
        Period p1 = Period.of(year, months, days);

        toNormalize(p1);
    }
}
```

**输出:**

```java
P12Y1M366D

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/period . html # normalized–](https://docs.oracle.com/javase/8/docs/api/java/time/Period.html#normalized--)