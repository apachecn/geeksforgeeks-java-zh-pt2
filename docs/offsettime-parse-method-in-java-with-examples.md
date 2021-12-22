# Java 中的 OffsetTime parse()方法，带示例

> 原文:[https://www . geesforgeks . org/offsettime-parse-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-parse-method-in-java-with-examples/)

在 OffsetTime 类中，根据传递给它的参数，有两种类型的 parse()方法。

### 解析(字符序列文本)

**parse()** 一个 **OffsetTime** 类的方法，用于从作为参数传递的字符串如“15:25:10+01:00”中获取 OffsetTime 的实例。该字符串必须具有有效的日期时间，并使用日期时间格式化程序进行分析。ISO_LOCAL_TIME。

**语法:**

```java
public static OffsetTime parse(CharSequence text)

```

**参数:**该方法只接受一个参数**文本**，即在 OffsetTime 中解析的文本。它不应为空。

**返回值:**该方法返回**偏移时间**，这是解析后的本地日期时间。

**异常:**如果文本无法解析，该方法抛出**datetime arseeexception**。

下面的程序说明了 parse()方法:
**程序 1:**

```java
// Java program to demonstrate
// OffsetTime.parse() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an OffsetTime object
        OffsetTime lt
            = OffsetTime.parse("15:25:10+01:00");

        // print result
        System.out.println("OffsetTime : "
                           + lt);
    }
}
```

**Output:**

```java
OffsetTime : 15:25:10+01:00

```

### 解析(字符序列文本，日期时间格式化程序格式化程序)

**parse()** 一个 **OffsetTime** 类的方法，用于从使用特定格式化程序作为参数传递的字符串(如“15:25:10+01:00”)中获取 OffsetTime 的实例。使用特定的格式化程序来解析日期时间。

**语法:**

```java
public static OffsetTime parse(CharSequence text,
                              DateTimeFormatter formatter)

```

**参数:**这个方法接受两个参数**文本**作为要解析的文本，**格式化程序**作为要使用的格式化程序。

**返回值:**该方法返回**偏移时间**，这是解析后的本地日期时间。

**异常:**如果文本无法解析，该方法抛出**datetime arseeexception**。

下面的程序说明了 parse()方法:
**程序 1:**

```java
// Java program to demonstrate
// OffsetTime.parse() method

import java.time.*;
import java.time.format.DateTimeFormatter;

public class GFG {
    public static void main(String[] args)
    {

        DateTimeFormatter dateTimeFormatter = DateTimeFormatter.ISO_OFFSET_TIME;

        // create an OffsetTime object and
        OffsetTime lt
            = OffsetTime
                  .parse("11:35:34+01:00",
                         dateTimeFormatter);

        // print result
        System.out.println("OffsetTime : "
                           + lt);
    }
}
```

**Output:**

```java
OffsetTime : 11:35:34+01:00

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # parse-Java . lang . charsequence-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#parse-java.lang.CharSequence-)