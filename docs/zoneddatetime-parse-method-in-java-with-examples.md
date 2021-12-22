# Java 中的 ZonedDateTime parse()方法，带示例

> 原文:[https://www . geeksforgeeks . org/zoneddatetime-parse-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneddatetime-parse-method-in-java-with-examples/)

在 ZonedDateTime 类中，根据传递给它的参数，有两种类型的 parse()方法。

### 解析(字符序列文本)

**parse()** 一个 **ZonedDateTime** 类的方法，用于从作为参数传递的字符串中获取 ZonedDateTime 的实例，如“2018-12-06t 19:21:12.123+05:30[Asia/加尔各答]”。该字符串必须具有有效的日期时间，并使用日期时间格式化程序进行分析。国际标准化组织分区日期时间。

**语法:**

```java
public static ZonedDateTime parse(CharSequence text)

```

**参数:**该方法只接受一个参数**文本**，即 ZonedDateTime 中要解析的文本。它不应为空。

**返回值:**该方法返回**区域日期时间**，即解析后的本地日期时间。

**异常:**如果文本无法解析，该方法抛出**datetime arseeexception**。

下面的程序说明了 parse()方法:

**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.parse() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an ZonedDateTime object
        ZonedDateTime zoneddatetime2
            = ZonedDateTime
                  .parse(
                      "2018-12-26T20:28:33.213+05:30[Asia/Calcutta]");

        // print result
        System.out.println("ZonedDateTime : "
                           + zoneddatetime2);
    }
}
```

**Output:**

```java
ZonedDateTime : 2018-12-26T20:28:33.213+05:30[Asia/Calcutta]

```

### 解析(字符序列文本，日期时间格式化程序格式化程序)

**parse()** 一个 **ZonedDateTime** 类的方法，用于从使用特定格式化程序作为参数传递的字符串中获取 ZonedDateTime 的实例，如“2018-12-06t 19:21:12.123+05:30[Asia/加尔各答]”。使用特定的格式化程序来解析日期时间。

**语法:**

```java
public static ZonedDateTime parse(CharSequence text,
                                  DateTimeFormatter formatter)

```

**参数:**这个方法接受两个参数**文本**作为要解析的文本，**格式化程序**作为要使用的格式化程序。

**返回值:**该方法返回**区域日期时间**，即解析后的本地日期时间。

**异常:**如果文本无法解析，该方法抛出**datetime arseeexception**。

下面的程序说明了 parse()方法:

**程序 1:**

```java
// Java program to demonstrate
// ZonedDateTime.parse() method

import java.time.*;
import java.time.format.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a formater
        DateTimeFormatter formatter
            = DateTimeFormatter
                  .ISO_ZONED_DATE_TIME;

        // create an ZonedDateTime object and
        ZonedDateTime zdt
            = ZonedDateTime
                  .parse("2018-12-16T20:28:33.213+05:30[Asia/Calcutta]",
                         formatter);

        // print result
        System.out.println("ZonedDateTime : "
                           + zdt);
    }
}
```

**Output:**

```java
ZonedDateTime : 2018-12-16T20:28:33.213+05:30[Asia/Calcutta]

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # parse(Java . lang . charsequence)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#parse(java.lang.CharSequence))
[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneddatetime . html # parse(Java . lang . charsequence，Java . time . format . datetime formatter)](https://docs.oracle.com/javase/10/docs/api/java/time/ZonedDateTime.html#parse(java.lang.CharSequence, java.time.format.DateTimeFormatter))