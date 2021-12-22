# Java 中的年范围()方法，示例

> 原文:[https://www . geesforgeks . org/year-range-in-Java-method-with-examples/](https://www.geeksforgeeks.org/year-range-method-in-java-with-examples/)

**范围()**年**类的**方法用于根据最小值和最大值获取字段的范围，字段作为参数传递给该方法。此方法的返回值是该字段的值范围对象，并且该方法只为年份对象支持的字段返回值范围对象。因此，当此方法不支持该字段时，此方法将引发异常。

**语法:**

```java
public ValueRange range(TemporalField field)

```

**参数:**该方法接受一个参数字段，即查询范围的字段。

**返回值:**此方法返回字段的有效值范围。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法获得字段的范围。
*   **unsupportedtemporaltypexception**–如果不支持该字段。

以下程序举例说明了 range()方法:
**程序 1:**

```java
// Java program to demonstrate
// Year.range() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create Year object
        Year year
            = Year.of(2017);

        // apply range() method of Year class
        ValueRange result
            = year.range(ChronoField.ERA);

        // print results
        System.out.println("Range in ERA: "
                           + result);
    }
}
```

**Output:**

```java
Range in ERA: 0 - 1

```

**程序 2:**

```java
// Java program to demonstrate
// Year.range() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create Year object
        Year year
            = Year.of(2017);

        // apply range() method of Year class
        ValueRange result
            = year.range(ChronoField.YEAR);

        // print results
        System.out.println("Range in YEAR: "
                           + result);
    }
}
```

**Output:**

```java
Range in YEAR: -999999999 - 999999999

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/year . html # range(Java . time . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/Year.html#range(java.time.temporal.TemporalField))