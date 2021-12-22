# Java 中的 Year minusYears()方法，带示例

> 原文:[https://www . geeksforgeeks . org/year-MINUS years-in-Java-method-in-with-examples/](https://www.geeksforgeeks.org/year-minusyears-method-in-java-with-examples/)

**年()**法**年**类习惯于从今年减去指定年数后得到今年的副本。
这个实例是不可变的，不受这个方法调用的影响。

**语法:**

```
public Year minusYears(long yearsToSubtract)

```

**参数:**该方法接受**年到子轨迹**作为参数，该参数是要减去的年，可以是负数。

**返回值:**此方法根据今年减去当年返回年。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果结果超出支持的范围。

以下程序说明了负年()方法:
**程序 1:**

```
// Java program to demonstrate
// Year.minusYears() method

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

        // apply minusYears method
        Year value
            = year.minusYears(20);

        // print result
        System.out.println("After subtraction year: "
                           + value);
    }
}
```

**Output:**

```
Year :2019
After subtraction year: 1999

```

**程序 2:**

```
// Java program to demonstrate
// Year.minusYears() method

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

        // apply minusYears method
        Year value
            = year.minusYears(1200);

        // print result
        System.out.println("After subtraction year: "
                           + value);
    }
}
```

**Output:**

```
Year :2019
After subtraction year: 819

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/year . html # MINUS years(长)](https://docs.oracle.com/javase/10/docs/api/java/time/Year.html#minusYears(long))