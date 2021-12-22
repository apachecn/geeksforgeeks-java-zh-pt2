# Java 中的 YearMonth atEndOfMonth()方法

> 原文:[https://www . geesforgeks . org/year month-atendofmonth-method-in-Java/](https://www.geeksforgeeks.org/yearmonth-atendofmonth-method-in-java/)

Java 中 YearMonth 类的 atEndOfMonth()方法用于根据使用它的 YearMonth 对象返回每月最后一天的 LocalDate。

**语法**:

```java
public LocalDate atEndOfMonth()

```

**参数**:该方法不接受任何参数。

**返回值**:返回一个本地日期，由 YearMonth 对象指定的是当月的最后一天。此方法不返回空值。

下面的程序说明了 Java 中的一年一月的方法:
**程序 1** :

```java
// Programt to illustrate the atEndOfMonth() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // Creates a YearMonth object
        YearMonth thisYearMonth = YearMonth.of(2017, 8);

        // Creates a local date with this
        // YearMonth object passed to it
        // Last day of this month is 31
        LocalDate date = thisYearMonth.atEndOfMonth();

        System.out.println(date);
    }
}
```

**Output:**

```java
2017-08-31

```

**程序二**:这个方法也照顾闰年。

```java
// Programt to illustrate the atEndOfMonth() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // Creates a YearMonth object
        YearMonth thisYearMonth = YearMonth.of(2016, 2);

        // Creates a local date with this
        // YearMonth object passed to it
        // Last day of February is
        // 29 as 2016 is a leap year
        LocalDate date = thisYearMonth.atEndOfMonth();

        System.out.println(date);
    }
}
```

**Output:**

```java
2016-02-29

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year month . html # atEndOfMonth–](https://docs.oracle.com/javase/8/docs/api/java/time/YearMonth.html#atEndOfMonth--)