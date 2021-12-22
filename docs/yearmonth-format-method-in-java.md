# Java 中的 YearMonth 格式()方法

> 原文:[https://www . geesforgeks . org/year-month-format-method-in-Java/](https://www.geeksforgeeks.org/yearmonth-format-method-in-java/)

Java 中 YearMonth 类的 format()方法用于根据作为参数传递给此方法的年-月的指定日期时间格式化程序格式化此 YearMonth 实例。

**语法**:

```
public String format(DateTimeFormatter formatter)
```

**参数**:这个方法接受一个单一的参数*格式化程序*，它是日期时间格式化程序，根据它来格式化这个年月实例。
**返回值**:按照指定的格式化程序格式化后，以字符串形式返回本年度月的值。
下面的程序说明了 Java 中 YearMonth 的格式()方法:
**程序 1** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Program to illustrate the format() method

import java.util.*;
import java.time.*;
import java.time.format.DateTimeFormatter;

public class GfG {
    public static void main(String[] args)
    {

        // Create a YearMonth object
        YearMonth thisYearMonth = YearMonth.of(2017, 8);

        // Create a DateTimeFormatter string
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yy/MM");

        // Format this year-month
        System.out.println(thisYearMonth.format(formatter));
    }
}
```

**Output:** 

```
17/08
```