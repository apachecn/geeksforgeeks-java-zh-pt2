# YearMonth isBefore()方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/year month-is before-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-isbefore-method-in-java-with-examples/)

Java 中 **Year 类的 **isBefore()** 方法用于检查当前的 YearMonth 对象是否在作为该方法参数指定的 YearMonth 之前。**

**语法** :

```
public boolean isBefore(Year otherYearMonth)

```

**参数**:接受单个参数 ***otherYearMonth*** ，与当前 YearMonth 对象进行比较。

**返回值**:如果这个 YearMonth 对象的值在作为方法参数指定的 YearMonth 对象的值之前，则返回一个**布尔值** True 值，否则返回 False。

下面的程序说明了 Java 中的 YearMonth.isBefore()方法:

**程序 1** :

```
// Program to illustrate the isBefore() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create first Year object
        YearMonth yearMonth1
            = YearMonth.of(2018, 3);

        // Create second Year object
        YearMonth yearMonth2
            = YearMonth.of(1997, 4);

        // Check if this year-month object's value is
        // before the specified Year-month or not
        System.out.println(yearMonth1
                               .isBefore(yearMonth2));
    }
}
```

**输出:**

```
false

```

**程序二** :

```
// Program to illustrate the isBefore() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create first Year object
        YearMonth yearMonth1
            = YearMonth.of(1997, 3);

        // Create second Year object
        YearMonth yearMonth2
            = YearMonth.of(2018, 4);

        // Check if this year-month object's value is
        // before the specified Year-month or not
        System.out.println(yearMonth1
                               .isBefore(yearMonth2));
    }
}
```

**输出:**

```
true

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year month . html # is before-Java . time . year month-](https://docs.oracle.com/javase/8/docs/api/java/time/YearMonth.html#isBefore-java.time.YearMonth-)