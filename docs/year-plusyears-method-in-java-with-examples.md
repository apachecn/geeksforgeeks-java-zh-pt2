# Java 中的 Year plusYears()方法，带示例

> 原文:[https://www . geesforgeks . org/year-plus yers-in-Java-method-with-examples/](https://www.geeksforgeeks.org/year-plusyears-method-in-java-with-examples/)

**plusYears()** 法的**年**类习惯于将指定的年数加到今年后复制一份今年。
这个实例是不可变的，不受这个方法调用的影响。

**语法:**

```
public Year plusYears(long yearsToadd)

```

**参数:**该方法接受**年数加**作为参数，该参数是要加的年数，可以是负数。

**返回值:**该方法根据今年加上年份返回年份。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果结果超出支持的范围。

以下程序说明了 plusYears()方法:
**程序 1:**

```
// Java program to demonstrate
// Year.plusYears() method

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

        // apply plusYears method
        Year value
            = year.plusYears(20);

        // print result
        System.out.println("After addition year: "
                           + value);
    }
}
```

**Output:**

```
Year :2019
After addition year: 2039

```

**程序 2:**

```
// Java program to demonstrate
// Year.plusYears() method

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

        // apply plusYears method
        Year value
            = year.plusYears(1200);

        // print result
        System.out.println("After addition year: "
                           + value);
    }
}
```

**Output:**

```
Year :2019
After addition year: 3219

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/year . html # plusYears(长)](https://docs.oracle.com/javase/10/docs/api/java/time/Year.html#plusYears(long))