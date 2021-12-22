# Java 中的 YearMonth getLong()方法，带示例

> 原文:[https://www . geesforgeks . org/year month-getlong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-getlong-method-in-java-with-examples/)

Java 中 **YearMonth** 类的 **getLong()** 方法用于从这个 year-month 中获取指定字段的值作为 Long 值。此方法查询今年-月指定字段的值。如果由于字段不受支持或其他原因而无法返回值，则会引发异常。

**语法:**

```java
public long getLong(TemporalField field)
```

**参数:**该方法接受**字段**作为参数，该参数表示需要其值的临时字段。

**返回值:**该方法将字段的值作为**长**返回。

**异常:**此方法抛出以下异常:

*   **[Date and Time Exception]** –If the value of this field cannot be obtained or it is beyond the valid range of this field.
*   **Unsupported Temporaltypeexception** –If the field is unsupported or the range of values exceeds an integer.
*   **Arithmetic exception** -If there is a numerical overflow.

下面的程序说明了 Java 中 YearMonth 的 getLong()方法:

**程序 1:**

```java
// Java program to demonstrate
// YearMonth.getLong() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create YearMonth object
        YearMonth yearmonth
            = YearMonth.of(2019, 4);

        // apply getLong() method
        // of YearMonth class to get year
        long year
            = yearmonth.getLong(
                ChronoField.YEAR_OF_ERA);
        // It will store only year
        // in variable of type long

        // print results
        System.out.println("YEAR: " + year);
    }
}
```

**输出:**

```java
YEAR: 2019

```

**程序二:**

```java
// Java program to demonstrate
// YearMonth.getLong() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create YearMonth object
        YearMonth yearmonth
            = YearMonth.of(2019, 4);

        // apply getLong() method
        // of YearMonth class to get month
        long month
            = yearmonth.getLong(
                ChronoField.MONTH_OF_YEAR);
        // It will store only month
        // in variable of type long

        // print results
        System.out.println("MONTH: " + month);
    }
}
```

**输出:**

```java
MONTH: 4

```

**参考文献:**T2