# Java 中的 OffsetDateTime 格式()方法，带示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-format-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-format-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **format()** 方法使用指定的格式化程序格式化这个日期时间。

**语法:**

```java
public String format(DateTimeFormatter formatter)
```

**参数:**此方法接受单个参数**格式化程序**，该参数指定要使用的格式化程序，而不是空值。
**返回值:**返回格式化的日期字符串，不为空。
**异常**:函数抛出**日期时间异常**，即打印过程中出现错误。
以下程序说明*格式()*方法:
**程序 1 :**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the format() method
import java.time.OffsetDateTime;
import java.time.format.DateTimeFormatter;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the date1
        OffsetDateTime date1 = OffsetDateTime.parse("2018-12-12T13:30:30+05:00");

        // Prints the date
        System.out.println("Date1: " + date1);

        DateTimeFormatter formatter = DateTimeFormatter.ISO_TIME;
        System.out.println(formatter.format(date1));
    }
}
```

**Output:** 

```java
Date1: 2018-12-12T13:30:30+05:00
13:30:30+05:00
```