# Java 中的年减(TemporalAmount)方法，示例

> 原文:[https://www . geeksforgeeks . org/year-minsteralamount-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-minustemporalamount-method-in-java-with-examples/)

**Year** 类的**减(临时金额)**方法，用于从 Year 对象中减去指定金额的临时金额后返回一份今年的副本。如果不能从年份中减去指定的单位，将引发异常。传递的临时计数是从周期对象创建的。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public Year minus(TemporalAmount amountToSubtract)

```

**参数:**此方法只接受一个参数**临时金额**，代表从年对象中减去的金额。

**返回值:**此方法返回一个基于本年度减去指定金额的年份。

**异常:**该方法抛出以下异常:

*   **datetime exception–**如果无法进行减法运算，则会引发此异常。
*   **算术异常–**如果出现数值溢出，将引发此异常。

下面的程序说明了负(临时数量)方法:

**程序 1:**

```java
// Java program to demonstrate
// Year.minus(TemporalAmount amountToSubtract) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a Year object
        Year year = Year.of(2019);

        // print instance
        System.out.println("Year :"
                           + year);

        // create temporalAmount object from period class
        // passing temporalAmount to
        // minus() method
        Year value
            = year.minus(
                Period.ofYears(40));

        // print result
        System.out.println("Value after Subtraction: "
                           + value);
    }
}
```

**Output:**

```java
Year :2019
Value after Subtraction: 1979

```

**程序 2:**

```java
// Java program to demonstrate
// Year.minus(TemporalAmount amountToSubtract) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a Year object
        Year year = Year.of(2019);

        // print instance
        System.out.println("Year :"
                           + year);

        // create temporalAmount object from period class
        // passing temporalAmount to
        // minus() method
        Year value
            = year.minus(
                Period.ofYears(20));

        // print result
        System.out.println("Value after Subtraction: "
                           + value);
    }
}
```

**Output:**

```java
Year :2019
Value after Subtraction: 1999

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/year . html #减(java.time .时态. tempalamount)](https://docs.oracle.com/javase/10/docs/api/java/time/Year.html#minus(java.time.temporal.TemporalAmount))