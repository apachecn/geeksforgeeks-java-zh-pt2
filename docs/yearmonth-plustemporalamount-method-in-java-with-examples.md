# Java 中的年月加(TemporalAmount)方法，示例

> 原文:[https://www . geesforgeks . org/year month-plustemporalamount-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-plustemporalamount-method-in-java-with-examples/)

**YearMonth** 类的**plus(temporalamont)**方法是将指定数量的 temporalamont 添加到 YearMonth 对象后，返回该 YearMonth 的副本。如果指定的单位不能添加到年月，将引发异常。传递的临时计数是从周期对象创建的。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public YearMonth plus(TemporalAmount amountToadd)
```

**参数:**该方法只接受一个参数**临时金额**，表示要添加到年月对象的金额。

**返回值:**该方法根据该年月返回一个年月，并加上指定的金额。

**异常:**该方法抛出以下异常:

*   **datetime exception–**如果无法进行加法运算，则会引发此异常。
*   **算术异常–**如果出现数值溢出，将引发此异常。

下面的程序说明了 plus(临时数量增加)方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// YearMonth.plus(TemporalAmount amountToadd) method

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
        // plus() method
        YearMonth value
            = thisYearMonth.plus(
                Period.ofYears(120));

        // print result
        System.out.println("Value after addition: "
                           + value);
    }
}
```

**Output:** 

```java
YearMonth :2019-11
Value after addition: 2139-11
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// YearMonth.plus(TemporalAmount amountToadd) method

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
        // plus() method
        YearMonth value
            = thisYearMonth.plus(
                Period.ofMonths(200));

        // print result
        System.out.println("Value after addition: "
                           + value);
    }
}
```

**Output:** 

```java
YearMonth :2022-11
Value after addition: 2039-07
```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html # plus(Java . time . temporal mount)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#plus(java.time.temporal.TemporalAmount))