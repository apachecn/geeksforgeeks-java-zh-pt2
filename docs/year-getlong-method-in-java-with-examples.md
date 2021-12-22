# Java 中 Year getLong()方法，带示例

> 原文:[https://www . geesforgeks . org/year-getlong-in-Java-method-with-examples/](https://www.geeksforgeeks.org/year-getlong-method-in-java-with-examples/)

**getLong()** 方法的 **Year** 类用于从今年开始为作为参数传递的指定字段获取值作为长值。此方法在今年查询字段的值，返回值将始终在字段值的有效范围内。当字段不受支持并且方法无法返回 int 值时，将引发异常。

**语法:**

```java
public long getLong(TemporalField field)

```

**参数:**该方法接受**字段**作为参数，该参数是要获取的字段。

**返回值:**该方法返回字段的值。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法获得该字段的值或该值超出了该字段的有效值范围。
*   **unsupportedtemporaltypexception**–如果字段不受支持或值的范围超过一个整数。
*   **算术异常**–如果出现数值溢出。

下面的程序说明了 getLong()方法:
**程序 1:**

```java
// Java program to demonstrate
// Year.getLong() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a Year object
        Year year = Year.of(2019);

        // print instance
        System.out.println("Year :"
                           + year);

        // apply getLong method
        long value
            = year.getLong(ChronoField.YEAR_OF_ERA);

        // print result
        System.out.println("YEAR_OF_ERA Field: "
                           + value);
    }
}
```

**Output:**

```java
Year :2019
YEAR_OF_ERA Field: 2019

```

**程序 2:**

```java
// Java program to demonstrate
// Year.getLong() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a Year object
        Year year = Year.of(2019);

        // print instance
        System.out.println("Year :"
                           + year);

        // apply getLong method
        long value
            = year.getLong(ChronoField.YEAR);

        // print result
        System.out.println("YEAR Field: "
                           + value);
    }
}
```

**Output:**

```java
Year :2019
YEAR Field: 2019

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/year . html # getLong(Java . time . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/Year.html#getLong(java.time.temporal.TemporalField))