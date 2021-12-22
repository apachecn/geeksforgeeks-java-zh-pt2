# Java 中的年加(TemporalAmount)方法，示例

> 原文:[https://www . geesforgeks . org/year-plustemporalamount-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-plustemporalamount-method-in-java-with-examples/)

**Year** 类的**plus(temporalamont)**方法是将指定金额的 temporalamont 添加到 Year 对象后返回一份今年的副本。如果指定的单位不能添加到年份，将引发异常。传递的临时计数是从周期对象创建的。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public Year plus(TemporalAmount amountToadd)

```

**参数:**此方法只接受一个参数**临时金额**，代表要添加到年份对象的金额。

**返回值:**该方法返回一个基于该年的年份，并加上指定的金额。

**异常:**该方法抛出以下异常:

*   **datetime exception–**如果无法进行加法运算，则会引发此异常。
*   **算术异常–**如果出现数值溢出，将引发此异常。

下面的程序说明了 plus(临时数量增加)方法:

**程序 1:**

```java
// Java program to demonstrate
// Year.plus(TemporalAmount amountToadd) method

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
        // plus() method
        Year value
            = year.plus(
                Period.ofYears(12));

        // print result
        System.out.println("Value after addition: "
                           + value);
    }
}
```

**Output:**

```java
Year :2019
Value after addition: 2031

```

**程序 2:**

```java
// Java program to demonstrate
// Year.plus(TemporalAmount amountToadd) method

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
        // plus() method
        Year value
            = year.plus(
                Period.ofYears(120));

        // print result
        System.out.println("Value after addition: "
                           + value);
    }
}
```

**Output:**

```java
Year :2019
Value after addition: 2139

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/year . html # plus(Java . time .时态. tempalamount)](https://docs.oracle.com/javase/10/docs/api/java/time/Year.html#plus(java.time.temporal.TemporalAmount))