# 年月发布 Java 支持的(临时)方法，示例

> 原文:[https://www . geesforgeks . org/year month-issupportedtemporalunit-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-issupportedtemporalunit-method-in-java-with-examples/)

**年月**类的**isSupported(TemporalUnit)**方法用于检查年月类是否支持指定的 TemporalUnit。实际上，这个方法检查我们是否可以使用传递的单位对指定的单位应用加法或减法运算。如果为 false，则调用加号(long，TemporalUnit)和减号方法将引发异常。

支持的计时单位是:

*   月份
*   年
*   数十年
*   世纪
*   一千年
*   年代

所有其他计时单位实例将返回 false。

**语法:**

```
public boolean isSupported(TemporalUnit unit)

```

**参数:**该方法只接受一个代表时间单位的参数**单位**进行检查。

**返回值:**该方法返回一个布尔值 *true* 如果该单位在本年度月受支持， *false* 如果不是。

以下程序说明了发布支持(临时)方法:
**程序 1:**

```
// Java program to demonstrate
// YearMonth.isSupported(TemporalUnit) method

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

        // apply isSupported() method
        boolean value
            = thisYearMonth.isSupported(
                ChronoUnit.MONTHS);

        // print result
        System.out.println("MONTHS unit is supported by YearMonth class: "
                           + value);
    }
}
```

**Output:**

```
YearMonth :2017-08
MONTHS unit is supported by YearMonth class: true

```

**程序 2:**

```
// Java program to demonstrate
// YearMonth.isSupported(TemporalUnit) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a YearMonth object
        YearMonth thisYearMonth = YearMonth.of(2022, 12);

        // print instance
        System.out.println("YearMonth :"
                           + thisYearMonth);

        // apply isSupported() method
        boolean value
            = thisYearMonth.isSupported(
                ChronoUnit.MILLENNIA);

        // print result
        System.out.println("MILLENNIA unit is supported: "
                           + value);
    }
}
```

**Output:**

```
YearMonth :2022-12
MILLENNIA unit is supported: true

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html # isSupported(Java . time . temporalunit)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#isSupported(java.time.temporal.TemporaUnit))