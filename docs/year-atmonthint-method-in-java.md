# Java 中的 Year atMonth(int)方法

> 原文:[https://www . geesforgeks . org/year-atmonthint-method-in-Java/](https://www.geeksforgeeks.org/year-atmonthint-method-in-java/)

Java 中 year 类的 atMonth(int)方法将当前的 Year 对象与作为参数传递给它的 Month 相结合，创建 YearMonth 对象。

**语法**:

```
public YearMonth atMonth(int month)

```

**参数**:此方法接受单个参数*月*。这是一年中使用的月份。它采用 1 到 12 之间的整数值，不能为空。

**返回值**:返回当前年对象形成的 YearMonth 对象和作为参数传递给函数的有效月份。

**异常**:如果作为参数传递给它的月份无效，这个方法抛出**日期时间异常**。

下面的程序用 Java 说明了一年中的第几个月(int)方法:
**程序 1** :

```
// Program to illustrate the atMonth(int) method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Creates a Year object
        Year thisYear = Year.of(2017);

        // Creates a YearMonth with this
        // Year object and Month passed to it
        YearMonth yearMonth = thisYear.atMonth(4);

        System.out.println(yearMonth);
    }
}
```

**Output:**

```
2017-04

```

**程序 2** :说明异常。

```
// Program to illustrate the atMonth(int) method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Creates a Year object
        Year thisYear = Year.of(2018);

        try {
            // Creates a YearMonth with this
            // Year object and Month passed to it
            YearMonth yearMonth = thisYear.atMonth(16);

            System.out.println(yearMonth);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
java.time.DateTimeException: Invalid value for MonthOfYear (valid values 1 - 12): 16

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year . html # atMonth-](https://docs.oracle.com/javase/8/docs/api/java/time/Year.html#atMonth-)