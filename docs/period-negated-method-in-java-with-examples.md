# Java 中的周期求反()方法，示例

> 原文:[https://www . geesforgeks . org/period-invalid-method-in-Java-with-examples/](https://www.geeksforgeeks.org/period-negated-method-in-java-with-examples/)

Java 中 Period 类的 invalid()方法用于在否定了 period YEAR、MONTH、DAY 的所有元素后返回 Period 的新实例。

**语法:**

```
public Period negated()
```

**参数:**该方法不接受任何参数。

**返回值:**这个方法在否定了 period 的每个元素后，返回一个 Period 的新实例。

**异常:**它抛出一个**算术异常**。如果发生数字溢出，将捕获此异常。

下面的程序说明了上面的方法:

**程序 1** :

```
// Java code to show the function to negate all
// elements of the period
import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodClass {

    // Function to negate given periods
    static void toNegate(Period p1)
    {

        System.out.println(p1.negated());
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Defining period
        int year = 4;
        int months = 11;
        int days = 10;
        Period p1 = Period.of(year, months, days);

        toNegate(p1);
    }
}
```

**输出:**

```
P-4Y-11M-10D

```

**程序二** :

```
// Java code to show the function to negate all
// elements of the period
import java.time.Period;
import java.time.temporal.ChronoUnit;

public class PeriodClass {

    // Function to negate given periods
    static void toNegate(Period p1)
    {

        System.out.println(p1.negated());
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Defining period
        int year = -4;
        int months = -11;
        int days = -10;
        Period p1 = Period.of(year, months, days);

        toNegate(p1);
    }
}
```

**输出:**

```
P4Y11M10D

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/period . html #否定–](https://docs.oracle.com/javase/8/docs/api/java/time/Period.html#negated--)