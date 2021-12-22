# Java 中的年解析(CharSequence，DateTimeFormatter)方法，示例

> 原文:[https://www . geeksforgeeks . org/year-parsecharsequencedetimeformatter-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-parsecharsequencedatetimeformatter-method-in-java-with-examples/)

**Year** 类的 **Year.parse(CharSequence，DateTimeFormatter)** 方法用于从使用 specificDateTimeFormatter 作为参数传递的字符串(如“2018”)中获取 Year 的实例。使用特定的日期时间格式化程序分析年份。该字符串必须具有可转换为年份的有效值。0000 到 9999 范围之外的年份必须以加号或减号作为前缀。

**语法:**

```
public static Year parse(CharSequence text,
                         DateTimeFormatter formatter)

```

**参数:**
该方法接受两个参数**文本**表示要解析的文本，如“2021”和**格式化程序**表示要使用的格式化程序。

**返回值:**
该方法返回解析后的年份。

**异常:**该方法抛出以下异常:

*   **如果文本无法解析，则为 datetime exception–**。

下面的程序说明了解析(CharSequence，DateTimeFormatter)方法:
**程序 1:**

```
// Java program to demonstrate
// Year.parse(CharSequence, DateTimeFormatter) method

import java.time.*;
import java.time.format.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a formater
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yy");

        // create a Year object
        // using parse(CharSequence, DateTimeFormatter)
        Year year = Year.parse("18", formatter);

        // print instance
        System.out.println("Year Parsed:"
                           + year);
    }
}
```

**Output:**

```
Year Parsed:2018

```

**程序 2:**

```
// Java program to demonstrate
// Year.parse(CharSequence, formatter) method

import java.time.*;
import java.time.format.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a formater
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy");

        // create a Year object
        // using parse(CharSequence, DateTimeFormatter)
        Year year = Year.parse("2087", formatter);

        // print instance
        System.out.println("Year Parsed:"
                           + year);
    }
}
```

**Output:**

```
Year Parsed:2087

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/year . html # parse(Java . lang . charsequence，Java . time . format . datetime formatter)](https://docs.oracle.com/javase/10/docs/api/java/time/Year.html#parse(java.lang.CharSequence, java.time.format.DateTimeFormatter))