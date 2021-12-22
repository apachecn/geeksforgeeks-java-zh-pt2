# Java 中的年月减(长，单位)方法，示例

> 原文:[https://www . geesforgeks . org/year month-minlongunit-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-minuslongunit-method-in-java-with-examples/)

**年月**类的**减(长，单位)**方法，用于从这个年月对象中减去指定的时间单位后，返回这个年月的副本。如果不能从年-月中减去指定的单位，将引发异常。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public YearMonth minus(long amountToSubtract, TemporalUnit unit)

```

**参数:**该方法接受两个参数:

*   **amountToSubtract** :此参数表示结果中要减去的单位数量。
*   **单位**:此参数代表要减去的金额的单位。

**返回值:**该方法根据该年-月，减去指定的金额，返回一个年-月。

**异常:**该方法抛出以下异常:

*   **datetime exception–**如果无法进行减法运算，则会引发此异常。
*   **unsupportedtemporaltypexception–**如果不支持该单元，将引发此异常。
*   **算术异常–**如果出现数值溢出，将引发此异常。

下面的程序说明了减(长，单位)的方法:

**程序 1:**

```
// Java program to demonstrate
// YearMonth.minus(long, unit) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create a YearMonth object
        YearMonth thisYearMonth = YearMonth.of(2017, 8);

        // print instance
        System.out.println("YearMonth :"
                           + thisYearMonth);

        // apply minus(long, unit) method
        // subtracting 20 Years
        YearMonth value
            = thisYearMonth.minus(20, ChronoUnit.YEARS);

        // print result
        System.out.println("After subtraction YearMonth: "
                           + value);
    }
}
```

**Output:**

```
YearMonth :2017-08
After subtraction YearMonth: 1997-08

```

**程序 2:**

```
// Java program to demonstrate
// YearMonth.minus(long, unit) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create a YearMonth object
        YearMonth thisYearMonth = YearMonth.of(2019, 12);

        // print instance
        System.out.println("YearMonth :"
                           + thisYearMonth);

        // apply minus(long, unit) method
        // subtracting 30 Months
        YearMonth value
            = thisYearMonth.minus(30, ChronoUnit.MONTHS);

        // print result
        System.out.println("After subtraction YearMonth: "
                           + value);
    }
}
```

**Output:**

```
YearMonth :2019-12
After subtraction YearMonth: 2017-06

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html #减(long，Java . time . temporalunit)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#minus(long, java.time.temporal.TemporalUnit))