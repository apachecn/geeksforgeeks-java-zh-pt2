# Java 中的 getMonthValue()方法

> 原文:[https://www . geesforgeks . org/year month-getmonth value-method-in-Java/](https://www.geeksforgeeks.org/yearmonth-getmonthvalue-method-in-java/)

Java 中 getMonthValue 类的 getMonthValue()方法用于从使用它的 YearMonth 实例中获取月份字段的值。它以 1-12 之间的整数形式返回月份字段的值，表示从 1 月到 12 月的月份。

**语法**:

```java
public int getMonthValue()

```

**参数**:该方法不接受任何参数。

**返回值**:返回月字段的值，为 1-12 之间的整数，表示 1 月至 12 月的月份。

下面的程序说明了 Java 中的 getMonthValue()方法:
**程序 1** :

```java
// Program to illustrate the getMonthValue() method

import java.util.*;
import java.time.*;
import java.time.format.DateTimeFormatter;

public class GfG {
    public static void main(String[] args)
    {

        // Create a YearMonth object
        YearMonth thisYearMonth = YearMonth.of(2017, 8);

        // Get the month field
        System.out.println(thisYearMonth.getMonthValue());
    }
}
```

**Output:**

```java
8

```

**程序 2** :

```java
// Program to illustrate the getMonthValue() method

import java.util.*;
import java.time.*;
import java.time.format.DateTimeFormatter;

public class GfG {
    public static void main(String[] args)
    {

        // Create a YearMonth object
        YearMonth thisYearMonth = YearMonth.of(2018, 5);

        // Get the month field
        System.out.println(thisYearMonth.getMonthValue());
    }
}
```

**Output:**

```java
5

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year month . html # getmonthvvalue–](https://docs.oracle.com/javase/8/docs/api/java/time/YearMonth.html#getMonthValue--)