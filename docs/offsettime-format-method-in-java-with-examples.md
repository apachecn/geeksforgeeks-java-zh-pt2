# Java 中的 OffsetTime format()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsettime-format-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-format-method-in-java-with-examples/)

Java 中 OffsetTime 类的 **format()** 方法这次使用在函数参数中传递的指定格式化程序进行格式化。

**语法:**

```java
public String format(DateTimeFormatter formatter)

```

**参数:**这个方法接受一个单一的强制参数**格式化程序**，指定要使用的格式化程序，并且不为空。

**返回值:**返回格式化的日期字符串，不为空。

**异常**:函数返回**日期时间异常**，该异常是在打印过程中出现错误时由方法抛出的。

以下程序说明了*格式()*方法:

**程序 1 :**

```java
// Java program to demonstrate the format() method

import java.time.OffsetTime;
import java.time.format.DateTimeFormatter;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the given time
        OffsetTime time
            = OffsetTime.parse("15:45:35+06:02");

        // Prints the parsed time
        System.out.println("Time: "
                           + time);

        // Function used
        DateTimeFormatter formatter
            = DateTimeFormatter.ISO_TIME;

        // Prints the formatted time
        System.out.println("Formatted time: "
                           + formatter.format(time));
    }
}
```

**输出:**

```java
Time: 15:45:35+06:02
Formatted time: 15:45:35+06:02

```

**程序二** :

```java
// Java program to demonstrate the format() method

import java.time.OffsetTime;
import java.time.format.DateTimeFormatter;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the given time
        OffsetTime time
            = OffsetTime.parse("11:14:13+07:05");

        // Prints the parsed time
        System.out.println("Time: "
                           + time);

        // Function used
        DateTimeFormatter formatter
            = DateTimeFormatter.ISO_TIME;

        // Prints the formatted time
        System.out.println("Formatted time: "
                           + formatter.format(time));
    }
}
```

**输出:**

```java
Time: 11:14:13+07:05
Formatted time: 11:14:13+07:05

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # format-Java . time . format . datetimeformatter-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#format-java.time.format.DateTimeFormatter-)