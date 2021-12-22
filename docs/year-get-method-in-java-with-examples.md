# Java 中的 Year get()方法，示例

> 原文:[https://www . geesforgeks . org/year-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-get-method-in-java-with-examples/)

**get()****Year**类的方法，用于获取作为参数从今年作为整数值传递的指定字段的值。此方法今年查询字段的值，返回值将始终在字段值的有效范围内。当字段不受支持并且方法无法返回 int 值时，将引发异常。

**语法:**

```
public int get(TemporalField field)

```

**参数:**该方法接受**字段**作为参数，该参数是要获取的字段。

**返回值:**该方法返回字段的值。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法获得该字段的值或该值超出了该字段的有效值范围。
*   **unsupportedtemporaltypexception**–如果字段不受支持或值的范围超过一个整数。
*   **算术异常**–如果出现数值溢出。

下面的程序说明了 get()方法:
**程序 1:**

```
// Java program to demonstrate
// Year.get() method

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

        // apply get method
        int value
            = year.get(ChronoField.YEAR);

        // print result
        System.out.println("Year Field: "
                           + value);
    }
}
```

**Output:**

```
Year :2019
Year Field: 2019

```

**程序 2:**

```
// Java program to demonstrate
// Year.get() method

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

        // apply get method
        int value
            = year.get(ChronoField.ERA);

        // print result
        System.out.println("ERA Field: "
                           + value);
    }
}
```

**Output:**

```
Year :2019
ERA Field: 1

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/year . html # get(Java . time . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/Year.html#get(java.time.temporal.TemporalField))