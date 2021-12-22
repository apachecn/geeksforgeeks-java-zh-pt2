# Java 中的 OffsetTime getLong()方法，带示例

> 原文:[https://www . geesforgeks . org/offsettime-getlong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-getlong-method-in-java-with-examples/)

Java 中 OffsetTime 类的 **getLong()** 方法从此时开始将参数中指定字段的值作为 Long 获取。

**语法:**

```java
public long getLong(TemporalField field)
```

**参数:**该方法接受单个参数**字段**，指定要获取的字段，不为空。
**返回值:**返回该字段的值。
**错误和异常:**程序返回三个异常，描述如下:

*   **unsupportedtemporaltypexception:**如果不支持该字段或值的范围超过一个长整型数，则会引发该异常。
*   **DateTimeException:** 如果无法获取字段的值或该值超出了字段有效值的范围，则会引发该异常。
*   **算术异常:**如果出现数值溢出，则抛出

下面的程序说明了 getLong()方法:
**程序 1 :**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the getLong() method

import java.time.OffsetTime;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {
        // Parses the time
        OffsetTime time = OffsetTime.parse("11:10:10+11:00");
        System.out.println("Gets the long time: "
               + time.getLong(ChronoField.CLOCK_HOUR_OF_DAY));
    }
}
```

**Output:** 

```java
Gets the long time: 11
```

**程序 2** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the getLong() method
// Exceptions

import java.time.OffsetTime;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        try {

            // Parses the time
            OffsetTime time = OffsetTime.parse("11:10:10+11:00");
            System.out.println("Gets the long time: "
                   + time.getLong(ChronoField.CLOCK_HOUR_OF_DAY));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:** 

```java
Gets the long time: 11
```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # getLong-Java . time . temporal field-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#getLong-java.time.temporal.TemporalField-)