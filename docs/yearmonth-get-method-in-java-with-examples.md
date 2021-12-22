# Java 中的 YearMonth get()方法，示例

> 原文:[https://www . geesforgeks . org/year-month-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-get-method-in-java-with-examples/)

Java 中 **YearMonth** 类的 **get()** 方法用于从这个 year-month 中获取指定字段的值作为整数值。此方法查询今年-月指定字段的值。返回值将始终在有效范围内。如果由于字段不受支持或其他原因而无法返回值，则会引发异常。

**语法:**

```
public int get(TemporalField field)
```

**参数:**该方法接受**字段**作为参数，表示需要其值的临时字段。

**返回值:**该方法返回字段的值。

**异常:**该方法抛出以下异常:

*   **[Date and Time Exception]** –If the value of this field cannot be obtained or it is beyond the valid range of this field.
*   **Unsupported Temporaltypeexception** –If the field is unsupported or the range of values exceeds an integer.
*   **Arithmetic exception** -If there is a numerical overflow.

下面的程序说明了 Java 中 YearMonth 的 get()方法:

**程序 1:**

```
// Java program to demonstrate
// YearMonth.get() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create YearMonth object
        YearMonth yearmonth
            = YearMonth.of(2020, 5);

        // apply get() method of
        // YearMonth class to get year
        // It will store year
        // in variable of type int
        int year
            = yearmonth.get(
                ChronoField.YEAR_OF_ERA);

        // print year
        System.out.println("YEAR: " + year);
    }
}
```

**输出:**

```
YEAR: 2020

```

**程序二:**

```
// Java program to demonstrate
// YearMonth.get() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create YearMonth object
        YearMonth yearmonth
            = YearMonth.of(2020, 5);

        // apply get() method of
        // YearMonth class to get month
        // It will store month
        // in variable of type int
        int month
            = yearmonth.get(
                ChronoField.MONTH_OF_YEAR);

        // print month
        System.out.println("MONTH: " + month);
    }
}
```

**输出:**

```
MONTH: 5

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html # get(Java . time . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#get(java.time.temporal.TemporalField))