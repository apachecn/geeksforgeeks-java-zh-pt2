# Java 中的年月长()方法，示例

> 原文:[https://www . geesforgeks . org/year month-length of year-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-lengthofyear-method-in-java-with-examples/)

Java 中 **YearMonth 类的 **lengthOfYear()** 方法**用来返回这个 year-month 对象值的年长度，以天数表示。根据年份是否为闰年，一年的长度值可以是 365 或 366。

**语法**:

```
public int lengthOfYear()

```

**参数**:该方法不接受任何参数。

**返回值**:返回一个以天数表示年长的**整数值**。

以下程序说明了 Java 中 YearMonth 的 lengthOfYear()方法:
**程序 1** :

```
// Program to illustrate the lengthOfYear() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create YearMonth object
        YearMonth yearMonth = YearMonth.of(2016, 2);

        // Print the length of year in Number
        // of days, 366 in this case as 2016 is
        // a Leap Year
        System.out.println(yearMonth.lengthOfYear());
    }
}
```

**Output:**

```
366

```

**程序 2** :

```
// Program to illustrate the lengthOfYear() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create YearMonth object
        YearMonth yearMonth = YearMonth.of(1990, 2);

        // Print the length of year in Number
        // of days, 365 in this case as 1990 is
        // not a Leap Year
        System.out.println(yearMonth.lengthOfYear());
    }
}
```

**Output:**

```
365

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year month . html # length of year–](https://docs.oracle.com/javase/8/docs/api/java/time/YearMonth.html#lengthOfYear--)