# Java 中的年月解析(CharSequence，DateTimeFormatter)方法，示例

> 原文:[https://www . geeksforgeeks . org/year month-parsersequencedetimeformatter-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-parsecharsequencedatetimeformatter-method-in-java-with-examples/)

**YearMonth** 类的**YearMonth . parse(CharSequence，DateTimeFormatter)** 方法用于从使用 specificDateTimeFormatter 作为参数传递的字符串(如“2018”)中获取 year month 的实例。使用特定的日期时间格式化程序分析年月。该字符串必须具有可转换为年月的有效值。

**语法:**

```
public static YearMonth parse(CharSequence text,
                         DateTimeFormatter formatter)

```

**参数:**
这个方法接受两个参数**文本**和**格式化器**，前者表示要解析的文本，后者表示要使用的格式化器。

**返回值:**
这个方法返回解析后的年月。

**异常:**该方法抛出以下异常:

*   **datetime exception–**如果无法解析文本，将引发此异常。

下面的程序说明了解析(CharSequence，DateTimeFormatter)方法:
**程序 1:**

```
// Java program to demonstrate
// YearMonth.parse(CharSequence, DateTimeFormatter) method

import java.time.*;
import java.time.format.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a formater
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yy-MM");

        // create a YearMonth object
        // using parse(CharSequence, DateTimeFormatter)
        YearMonth yearMonth = YearMonth.parse("18-02", formatter);

        // print instance
        System.out.println("YearMonth Parsed:"
                           + yearMonth);
    }
}
```

**Output:**

```
YearMonth Parsed:2018-02

```

**程序 2:**

```
// Java program to demonstrate
// YearMonth.parse(CharSequence, DateTimeFormatter) method

import java.time.*;
import java.time.format.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a formater
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy-MM");

        // create a YearMonth object
        // using parse(CharSequence, DateTimeFormatter)
        YearMonth yearMonth = YearMonth.parse("2100-09", formatter);

        // print instance
        System.out.println("YearMonth Parsed:"
                           + yearMonth);
    }
}
```

**Output:**

```
YearMonth Parsed:2100-09

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html # parse(Java . lang . charsequence，Java . time . format . datetime formatter)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#parse(java.lang.CharSequence, java.time.format.DateTimeFormatter))