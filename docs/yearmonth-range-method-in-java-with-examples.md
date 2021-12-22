# Java 中的年月范围()方法，示例

> 原文:[https://www . geesforgeks . org/year-month-range-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-range-method-in-java-with-examples/)

**range()****year month**类的方法，用于获取 ValueRange 对象，该对象是作为参数传递的字段的最小值和最大值的字段范围。该方法只为 YearMonth 对象支持的那些字段返回 ValueRange 对象。所以当这个方法不支持这个字段时，这个方法就会抛出一个异常。

**语法:**

```
public ValueRange range(TemporalField field)

```

**参数:**该方法接受一个参数字段，即查询范围的字段。

**返回值:**此方法返回字段的有效值范围。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法获得字段的范围。
*   **unsupportedtemporaltypexception**–如果不支持该字段。

以下程序举例说明了 range()方法:
**程序 1:**

```
// Java program to demonstrate
// YearMonth.range() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create YearMonth object
        YearMonth yearMonth
            = YearMonth.of(2017, 8);

        // apply range() method of YearMonth class
        ValueRange result
            = yearMonth.range(ChronoField.YEAR_OF_ERA);

        // print results
        System.out.println("Range in YEAR_OF_ERA: "
                           + result);
    }
}
```

**Output:**

```
Range in YEAR_OF_ERA: 1 - 999999999

```

**程序 2:**

```
// Java program to demonstrate
// YearMonth.range() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create YearMonth object
        YearMonth yearMonth
            = YearMonth.of(2017, 8);

        // apply range() method of YearMonth class
        ValueRange result
            = yearMonth.range(ChronoField.ERA);

        // print results
        System.out.println("Range in ERA: "
                           + result);
    }
}
```

**Output:**

```
Range in ERA: 0 - 1

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html # range(Java . time . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#range(java.time.temporal.TemporalField))