# Java 中的 YearMonth plusYears()方法，带示例

> 原文:[https://www . geesforgeks . org/year month-plusyears-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-plusyears-method-in-java-with-examples/)

Java 中 **YearMonth 类**的 **plusYears()** 方法用来返回这个 YearMonth 的一个副本，加上指定的年数。

**语法:**

```
public YearMonth plusYears(long yearsToAdd)
```

**参数:**此方法接受**年添加**作为参数，表示要添加到当前年月对象的年。可能是负面的。

**返回值:**根据这个年-月加上年份返回一个**年-月**。

**异常:**如果结果超出支持范围，该方法抛出**日期时间异常**。

下面的程序说明了 Java 中的年月 plusYears()方法:

**程序 1:**

```
// Java program to demonstrate
// YearMonth.plusYears() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create YearMonth object
        YearMonth yearmonth
            = YearMonth.parse("2020-05");

        // Apply plusYears() method
        // of YearMonth class
        YearMonth result
            = yearmonth.plusYears(5);
        // It will add 5 years into May 2020
        // So it will be May 2025

        // print results
        System.out.println(
            "Modified YearMonth: "
            + result);
    }
}
```

**输出:**

```
Modified YearMonth: 2025-05

```

**程序二:**

```
// Java program to demonstrate
// YearMonth.plusYears() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create YearMonth object
        YearMonth yearmonth
            = YearMonth.of(2019, 10);
        // It is October 2019

        // apply plusYears() method
        // of YearMonth class
        YearMonth result
            = yearmonth.plusYears(10);
        // YearMonth will become October 2029

        // print only modified year
        System.out.println(
            "Modified Year: "
            + result.get(ChronoField.YEAR));
    }
}
```

**输出:**

```
Modified Year: 2029

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html # plusYears(long)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#plusYears(long))