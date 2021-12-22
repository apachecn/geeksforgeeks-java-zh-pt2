# Java 中的年月 plusMonths()方法，带示例

> 原文:[https://www . geesforgeks . org/year month-plusmonths-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-plusmonths-method-in-java-with-examples/)

Java 中 **YearMonth** 类的 **plusMonths()** 方法用来获取这个添加了指定月数的 YearMonth 的副本。

**语法:**

```java
public YearMonth plusMonths(long monthsToAdd)
```

**参数:**此方法接受**月添加**作为参数，表示要添加到当前年月对象的月份。可能是负面的。

**返回值:**根据这个年-月加上月份，返回一个**年-月**。

**异常:**如果结果超出支持范围，该方法抛出**日期时间异常**。

下面的程序说明了 Java 中的年月 plusMonths()方法:

**程序 1:**

```java
// Java program to demonstrate
// YearMonth.plusMonths() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create YearMonth object
        YearMonth yearmonth
            = YearMonth.parse("2020-05");

        // apply plusMonths() method
        // of YearMonth class
        // Adding 5 months into May 2020
        // will turn it into October 2020
        YearMonth result = yearmonth.plusMonths(5);

        // print results
        System.out.println("Modified YearMonth: "
                           + result);
    }
}
```

**输出:**

```java
Modified YearMonth: 2020-10

```

**程序二:**

```java
// Java program to demonstrate
// YearMonth.plusMonths() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create YearMonth object
        YearMonth yearmonth
            = YearMonth.parse("2019-05");

        // apply plusMonths() method
        // of YearMonth class
        // Adding 10 months into it will turn
        // it to 3rd month of next year
        YearMonth result
            = yearmonth.plusMonths(10);

        // print results
        System.out.println("Modified YearMonth: "
                           + result);
    }
}
```

**输出:**

```java
Modified YearMonth: 2020-03

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html # plusMonths(长)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#plusMonths(long))