# Java 中的年月(int，Month)方法，示例

> 原文:[https://www . geesforgeks . org/year month-of it-month-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-ofint-month-method-in-java-with-examples/)

Java 中 **YearMonth** 类的(int year，Month month) 方法的**用于从年和月中获取 **YearMonth** 的实例。
**语法:****

```
public static YearMonth of(
    int year, Month month)
```

**参数:**该方法接受两个参数:

*   **年**:代表年。
*   **月**:代表一年中的月份。

**返回值:**此方法返回**年-月**。

**异常:**如果任何字段的值无效，该方法将抛出**日期时间异常**。

下面的程序说明了 Java 中 YearMonth 的(年、月、月)方法:

**程序 1:**

```
// Java program to demonstrate
// YearMonth.of(int year, Month month) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply of(int year, Month month) method
        // of YearMonth class
        YearMonth yearmonth
            = YearMonth.of(2020, Month.MAY);

        // print year and month
        System.out.println("YearMonth: "
                           + yearmonth);
    }
}
```

**Output:**

```
YearMonth: 2020-05

```

**程序 2:**

```
// Java program to demonstrate
// YearMonth.of(int year, Month month) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply of(int year, Month month) method
        // of YearMonth class
        YearMonth yearmonth
            = YearMonth.of(2020, Month.MAY);

        // print only year
        System.out.println("Year: "
                           + yearmonth.getYear());
    }
}
```

**Output:**

```
Year: 2020

```

**程序 3:**

```
// Java program to demonstrate
// YearMonth.of(int year, Month month) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply of(int year, Month month) method
        // of YearMonth class
        YearMonth yearmonth
            = YearMonth.of(2020, Month.MAY);

        // print only month
        System.out.println("Month: "
                           + yearmonth.getMonth());
    }
}
```

**Output:**

```
Month: MAY

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html # of(int，java.time.Month)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#of(int, java.time.Month))