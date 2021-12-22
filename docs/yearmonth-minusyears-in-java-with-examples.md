# Java 中的年月日(带示例)

> 原文:[https://www . geesforgeks . org/year month-MINUS-years-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-minusyears-in-java-with-examples/)

Java 中 **YearMonth** 类的**MINUS year()**方法用来返回这个 YearMonth 减去指定年数的副本。

**语法:**

```
public YearMonth minusYears(long yearsToSubtract)
```

**参数:**该方法接受**年到子轨迹**作为代表要减去的年的参数。可能是负面的。

**返回值:**根据这个年-月减去年，返回一个**年-月**。

**异常:**如果结果超出支持范围，该方法抛出**日期时间异常**。

下面的程序说明了 Java 中的年月的负年()方法:

**程序 1:**

```
// Java program to demonstrate
// YearMonth.minusYears() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create YearMonth object
        YearMonth yearmonth
            = YearMonth.parse("2020-05");
        // It is May 2020

        // apply minusYears() method
        // of YearMonth class
        YearMonth result
            = yearmonth.minusYears(5);
        // Subtracting 5 years will turn it
        // into May 2015

        // print year and month both
        System.out.println(
            "Modified YearMonth: "
            + result);
    }
}
```

**输出:**

```
Modified YearMonth: 2015-05

```

**程序二:**

```
// Java program to demonstrate
// YearMonth.minusYears() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create YearMonth object
        YearMonth yearmonth
            = YearMonth.of(2019, 10);

        // apply minusYears() method
        // of YearMonth class
        YearMonth result
            = yearmonth.minusYears(10);
        // Subtracting 10 years will
        // turn it into October 2009

        // print only year
        System.out.println(
            "Modified Year: "
            + result.get(ChronoField.YEAR));
    }
}
```

**输出:**

```
Modified Year: 2009

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html # MINUS years(长)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#minusYears(long))