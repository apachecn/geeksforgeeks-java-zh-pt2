# Java 中的年月月月()方法，示例

> 原文:[https://www . geesforgeks . org/year month-MINUS months-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-minusmonths-method-in-java-with-examples/)

Java 中 **YearMonth** 类的 **minusMonths()** 方法用来返回这个 YearMonth 减去指定月数的副本。
**语法:**

```
public YearMonth minusMonths(
        long monthsToSubtract)
```

**参数:**此方法接受**月到子轨迹**作为代表要减去的月份的参数。可能是负面的。
**返回值:**根据这个年-月减去月份，返回**年-月**。
**异常:**如果结果超出支持范围，该方法抛出 **DateTimeException** 。
下面的程序说明了 Java 中 YearMonth 的 MINUS()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// YearMonth.minusMonths() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create YearMonth object
        YearMonth yearmonth
            = YearMonth.parse("2020-05");
        // It is May 2020

        // apply minusMonths() method
        // of YearMonth class
        YearMonth result
            = yearmonth.minusMonths(2);
        // It subtracts 2 months from May 2020
        // So it will be March 2020

        // print year and month both
        System.out.println("Modified YearMonth: "
                           + result);
    }
}
```

**Output:** 

```
Modified YearMonth: 2020-03
```

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// YearMonth.minusMonths() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create YearMonth object
        YearMonth yearmonth
            = YearMonth.parse("2019-10");

        // apply minusMonths() method
        // of YearMonth class
        YearMonth result
            = yearmonth.minusMonths(10);
        // Subtracting 10 months will turn it into
        // December of 2018 (previous year)

        // print year and month both
        System.out.println(
            "Modified YearMonth: "
            + result);
    }
}
```

**Output:** 

```
Modified YearMonth: 2018-12
```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html # MINUS months(长)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#minusMonths(long))