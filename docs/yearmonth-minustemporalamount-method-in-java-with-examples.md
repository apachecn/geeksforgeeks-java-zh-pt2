# Java 中的年月减(TemporalAmount)方法，示例

> 原文:[https://www . geeksforgeeks . org/year month-minsteralamount-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-minustemporalamount-method-in-java-with-examples/)

**YearMonth** 类的**减(temporalamont)**方法用于在从 YearMonth 对象中减去指定数量的 temporalamont 后返回该 YearMonth 的副本。如果不能从年月中减去指定的单位，将引发异常。传递的临时计数是从周期对象创建的。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public YearMonth minus(TemporalAmount amountToSubtract)

```

**参数:**该方法只接受一个参数**临时账户**，表示从年月对象中减去的金额。

**返回值:**该方法根据该年月返回一个年月，减去指定的金额。

**异常:**该方法抛出以下异常:

*   **datetime exception–**如果无法进行减法运算，则会引发此异常。
*   **算术异常–**如果出现数值溢出，将引发此异常。

下面的程序说明了负(临时数量)方法:

**程序 1:**

```java
// Java program to demonstrate
// YearMonth.minus(TemporalAmount amountToSubtract) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a YearMonth object
        YearMonth thisYearMonth = YearMonth.of(2019, 11);

        // print instance
        System.out.println("YearMonth :"
                           + thisYearMonth);

        // create temporalAmount object from period class
        // passing temporalAmount to
        // minus() method
        YearMonth value
            = thisYearMonth.minus(
                Period.ofYears(22));

        // print result
        System.out.println("Value after Subtraction: "
                           + value);
    }
}
```

**Output:**

```java
YearMonth :2019-11
Value after Subtraction: 1997-11

```

**程序 2:**

```java
// Java program to demonstrate
// YearMonth.minus(TemporalAmount amountToSubtract) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a YearMonth object
        YearMonth thisYearMonth = YearMonth.of(2022, 11);

        // print instance
        System.out.println("YearMonth :"
                           + thisYearMonth);

        // create temporalAmount object from period class
        // passing temporalAmount to
        // minus() method
        YearMonth value
            = thisYearMonth.minus(
                Period.ofMonths(20));

        // print result
        System.out.println("Value after Subtraction: "
                           + value);
    }
}
```

**Output:**

```java
YearMonth :2022-11
Value after Subtraction: 2021-03

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html #减(Java . time . temporal mount)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#minus(java.time.temporal.TemporalAmount))