# Java 中的 OffsetDateTime get()方法，带示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-get-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **get()** 方法从这个日期开始，将指定字段的值作为 int 获取。

**语法:**

```
public int get(TemporalField field)
```

**参数:**该方法接受单个参数**字段**，指定要获取的字段，不为空。
**返回值:**返回该字段的值。
**异常**:函数抛出三个异常:

*   **DateTimeException** :如果无法获取字段的值或者该值超出了字段的有效值范围，则抛出。
*   **unsupportedtemporaltypexception**:如果不支持该字段或者值的范围超过一个整数，则抛出该异常
*   **算术异常**:出现数值溢出时抛出

下面的程序说明了 *get()* 方法:
T3】程序 1 :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the get() method

import java.time.OffsetDateTime;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // Function used
        OffsetDateTime date = OffsetDateTime.parse("2017-02-03T12:30:30+01:00");

        // Prints the date
        System.out.println(date.get(ChronoField.CLOCK_HOUR_OF_DAY));
    }
}
```

**Output:** 

```
12
```

**程序 2** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the get() method
// Exceptions

import java.time.OffsetDateTime;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {
        try {
            // Function used
            OffsetDateTime date = OffsetDateTime.parse("2017-13-03T12:30:30+01:00");

            // Prints the date
            System.out.println(date.get(ChronoField.CLOCK_HOUR_OF_DAY));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:** 

```
java.time.format.DateTimeParseException: Text '2017-13-03T12:30:30+01:00' could not be parsed: Invalid value for MonthOfYear (valid values 1 - 12): 13
```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsetdatetime . html # get-Java . time . temporal field-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetDateTime.html#get-java.time.temporal.TemporalField-)