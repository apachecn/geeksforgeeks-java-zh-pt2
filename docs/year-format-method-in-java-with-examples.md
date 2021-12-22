# Java 中的 Year 格式()方法，带示例

> 原文:[https://www . geesforgeks . org/year-format-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-format-method-in-java-with-examples/)

Java 中 Year 类的 format()方法用于根据作为参数传递给它的 DateTimeFormatter 格式化当前 Year 对象。

**语法**:

```java
public String format(DateTimeFormatter formatter)

```

**参数**:该方法接受单个参数*格式化程序*。它指定一个日期时间格式化程序，当前年份对象将根据该格式进行格式化。它不能为空。

**返回值**:返回一个字符串，是格式化的年份值。

**异常**:如果在格式化年对象的过程中出现任何错误，该方法将抛出**日期时间异常**。

下面的程序用 Java 说明了 Year 的格式()方法:
**程序 1** :

```java
// Program to illustrate the format() method

import java.util.*;
import java.time.*;
import java.time.format.DateTimeFormatter;

public class GfG {
    public static void main(String[] args)
    {
        // Creates a Year object
        Year firstYear = Year.of(1997);

        // Print the current year in
        // default format
        System.out.println(firstYear);

        // Create a DateTimeFormatter
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yy");

        // Print the current year after formatting
        System.out.println(firstYear.format(formatter));
    }
}
```

**Output:**

```java
1997
97

```

**程序 2** :

```java
// Program to illustrate the format() method

import java.util.*;
import java.time.*;
import java.time.format.DateTimeFormatter;

public class GfG {
    public static void main(String[] args)
    {
        // Creates a Year object
        Year firstYear = Year.of(2018);

        // Print the current year in
        // default format
        System.out.println(firstYear);

        // Create a DateTimeFormatter
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yy");

        // Print the current year after formatting
        System.out.println(firstYear.format(formatter));
    }
}
```

**Output:**

```java
2018
18

```

**参考**:
[https://docs . Oracle . com/javase/8/docs/API/Java/time/year . html # format-Java . time . format . datetime formatter-](https://docs.oracle.com/javase/8/docs/api/java/time/Year.html#format-java.time.format.DateTimeFormatter-)