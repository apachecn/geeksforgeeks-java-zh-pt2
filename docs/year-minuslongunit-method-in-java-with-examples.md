# Java 中的年减(长，单位)法，示例

> 原文:[https://www . geesforgeks . org/year-minlongunit-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-minuslongunit-method-in-java-with-examples/)

**Year** 类的**减(长，单位)**方法，用于从 Year 对象中减去指定数量的单位后返回一份今年的副本。如果不能从年份中减去指定的单位，将引发异常。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public Year minus(long amountToSubtract, TemporalUnit unit)

```

**参数:**该方法接受两个参数:

*   **amountToSubtract** :此参数表示结果中要减去的单位数量。
*   **单位**:此参数代表要减去的金额的单位。

**返回值:**此方法返回一个基于本年度减去指定金额的年份。

**异常:**该方法抛出以下异常:

*   **datetime exception–**如果无法进行减法运算，则会引发此异常。
*   **unsupportedtemporaltypexception–**如果不支持该单元，将引发此异常。
*   **算术异常–**如果出现数值溢出，将引发此异常。

下面的程序说明了减(长，单位)的方法:

**程序 1:**

```java
// Java program to demonstrate
// Year.minus(long, unit) method

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

        // apply minus(long, unit) method
        // subtracting 20 years
        Year value
            = year.minus(20, ChronoUnit.YEARS);

        // print result
        System.out.println("After subtraction year: "
                           + value);
    }
}
```

**Output:**

```java
Year :2019
After subtraction year: 1999

```

**程序 2:**

```java
// Java program to demonstrate
// Year.minus(long, unit) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a Year object
        Year year = Year.of(2022);

        // print instance
        System.out.println("Year :"
                           + year);

        // apply minus(long, unit) method
        // subtracting 30 years
        Year value
            = year.minus(30, ChronoUnit.YEARS);

        // print result
        System.out.println("After subtraction year: "
                           + value);
    }
}
```

**Output:**

```java
Year :2022
After subtraction year: 1992

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/year . html #减(long，Java . time . temporalunit)](https://docs.oracle.com/javase/10/docs/api/java/time/Year.html#minus(long, java.time.temporal.TemporalUnit))