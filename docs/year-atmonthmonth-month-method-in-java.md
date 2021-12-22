# Java 中的年月法

> 原文:[https://www . geesforgeks . org/year-at month-month-in-method-in-Java/](https://www.geeksforgeeks.org/year-atmonthmonth-month-method-in-java/)

Java 中 year 类的 atMonth(Month)方法将当前的 Year 对象与作为参数传递给它的 Month 相结合，创建 YearMonth 对象。

**语法**:

```
public YearMonth atMonth(Month month)

```

**参数**:此方法接受单个参数*月*。这是一年中使用的月份。它采用有效的月对象，不能为空。

**返回值**:返回当前年对象形成的 YearMonth 对象和作为参数传递给函数的有效月份。

下面的程序用 Java 说明了一年的第几个月的方法:
**程序 1** :

```
// Program to illustrate the atMonth(Month) method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Creates a Year object
        Year thisYear = Year.of(2017);

        // Creates a YearMonth with this
        // Year object and Month passed to it
        YearMonth yearMonth = thisYear.atMonth(Month.SEPTEMBER);

        System.out.println(yearMonth);
    }
}
```

**Output:**

```
2017-09

```

**程序 2** :

```
// Program to illustrate the atMonth(Month) method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Creates a Year object
        Year thisYear = Year.of(2018);

        // Creates a YearMonth with this
        // Year object and Month passed to it
        YearMonth yearMonth = thisYear.atMonth(Month.JANUARY);

        System.out.println(yearMonth);
    }
}
```

**Output:**

```
2018-01

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year . html # atMonth-](https://docs.oracle.com/javase/8/docs/api/java/time/Year.html#atMonth-)