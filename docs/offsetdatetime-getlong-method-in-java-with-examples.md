# Java 中的 OffsetDateTime getLong()方法，带示例

> 原文:[https://www . geesforgeks . org/offsetdatetime-getlong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsetdatetime-getlong-method-in-java-with-examples/)

Java 中 OffsetDateTime 类的 **getLong()** 方法从这个日期时间中获取指定字段的值作为一个 Long。

**语法:**

```java
public long getLong(TemporalField field)

```

**参数:**该方法接受单个参数**字段**，指定要获取的字段，不为空。

**返回值:**返回该字段的值。

**异常**:该函数抛出三个异常，描述如下:

*   **[Date and Time Exception]** : If the value of this field cannot be obtained or the value is beyond the valid range of this field, the exception will be thrown.
*   **Unsupported Temporaltypeexception** : If the field is not supported or the value range exceeds a long integer, it will be thrown.
*   **Arithmetic exception** : thrown when numerical value overflows.

以下程序说明了 *getLong()* 方法:

**程序 1 :**

```java
// Java program to demonstrate the getLong() method
import java.time.OffsetDateTime;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // parses a date
        OffsetDateTime date = OffsetDateTime.parse("2018-12-03T12:30:30+01:00");

        // Prints the value of the specified
        // field from this date-time as an long.
        System.out.println(date.getLong(ChronoField.CLOCK_HOUR_OF_DAY));
    }
}
```

**输出:**

```java
12

```

**程序二** :

```java
// Java program to demonstrate the getDayOfYear() method
// exceptions

import java.time.OffsetDateTime;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {
        try {
            // parses a date
            OffsetDateTime date = OffsetDateTime.parse("2018-24-03T12:30:30+01:00");

            // Prints the value of the specified
            // field from this date-time as an long.
            System.out.println(date.getLong(ChronoField.CLOCK_HOUR_OF_DAY));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
java.time.format.DateTimeParseException: 
Text '2018-24-03T12:30:30+01:00' could not be parsed: 
Invalid value for MonthOfYear (valid values 1 - 12): 24

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/temporal field . html](https://docs.oracle.com/javase/8/docs/api/java/time/temporal/TemporalField.html)