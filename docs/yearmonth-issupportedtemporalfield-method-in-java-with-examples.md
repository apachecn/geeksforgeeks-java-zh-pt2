# 年月发布支持的 Java(临时字段)方法，示例

> 原文:[https://www . geesforgeks . org/year month-issupportedtemporalfield-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-issupportedtemporalfield-method-in-java-with-examples/)

**YearMonth** 类的**isSupported(temporal field)**方法用于检查 YearMonth 类是否支持指定的字段，这意味着使用该方法我们可以检查指定字段是否可以查询到 YearMonth 对象。

计时场支持的字段有:

*   年月日
*   prolective _ MONTH
*   纪元年
*   年
*   时代

所有其他时间域实例都将返回 false。

**语法:**

```
public boolean isSupported(TemporalField field)

```

**参数:**此方法只接受一个参数**字段**，代表要检查的字段。

**返回值:**如果此年月支持该字段，则该方法返回布尔值 true，否则返回 false。

以下程序说明了问题支持(临时字段)方法:

**程序 1:**

```
// Java program to demonstrate
// YearMonth.isSupported(TemporalField) method

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
                ChronoField.PROLEPTIC_MONTH);

        // print result
        System.out.println("PROLEPTIC_MONTH Field is supported by YearMonth class: "
                           + value);
    }
}
```

**Output:**

```
YearMonth :2017-08
PROLEPTIC_MONTH Field is supported by YearMonth class: true

```

**程序 2:**

```
// Java program to demonstrate
// YearMonth.isSupported(TemporalField) method

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
                ChronoField.HOUR_OF_DAY);

        // print result
        System.out.println("HOUR_OF_DAY Field is supported by YearMonth class: "
                           + value);
    }
}
```

**Output:**

```
YearMonth :2017-08
HOUR_OF_DAY Field is supported by YearMonth class: false

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html # isSupported(Java . time . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#isSupported(java.time.temporal.TemporalField))