# Java 中的 YearMonth getYear()方法

> 原文:[https://www . geesforgeks . org/year month-get year-method-in-Java/](https://www.geeksforgeeks.org/yearmonth-getyear-method-in-java/)

Java 中 YearMonth 类的 getYear()方法用于从使用它的 YearMonth 实例中获取 Year 字段的值。它以从最小年到最大年的整数形式返回年字段的值。

**语法**:

```java
public int getYear()

```

**参数**:该方法不接受任何参数。

**返回值**:以 MIN_YEAR 到 MAX_YEAR 的整数形式返回年份字段的值。

下面的程序说明了 Java 中 YearMonth 的 getYear()方法:
**程序 1** :

```java
// Program to illustrate the getYear() method

import java.util.*;
import java.time.*;
import java.time.format.DateTimeFormatter;

public class GfG {
    public static void main(String[] args)
    {

        // Create a YearMonth object
        YearMonth thisYearMonth = YearMonth.of(2017, 8);

        // Get the year field
        System.out.println(thisYearMonth.getYear());
    }
}
```

**Output:**

```java
2017

```

**程序 2** :

```java
// Program to illustrate the getYear() method

import java.util.*;
import java.time.*;
import java.time.format.DateTimeFormatter;

public class GfG {
    public static void main(String[] args)
    {

        // Create a YearMonth object
        YearMonth thisYearMonth = YearMonth.of(2018, 5);

        // Get the year field
        System.out.println(thisYearMonth.getYear());
    }
}
```

**Output:**

```java
2018

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year month . html # getYear–](https://docs.oracle.com/javase/8/docs/api/java/time/YearMonth.html#getYear--)