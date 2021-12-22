# Java 中的 OffsetTime get()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsettime-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-get-method-in-java-with-examples/)

Java 中 OffsetTime 类的 **get()** 方法从此时起将指定字段的值作为 int 获取。
**语法:**

```java
public int get(TemporalField field)
```

**参数:**该方法接受一个参数**字段**，指定要获取的字段，不为空。
**返回值:**返回该字段的值。
异常:函数抛出三个异常，描述如下:

*   **unsupportedtemporaltypexception**:如果不支持该字段或者值的范围超过一个整数，则为真
*   **日期时间异常**:如果无法获取字段的值或者该值超出了字段有效值的范围，则为“是”。
*   **算术异常**:如果出现数值溢出，则为真

下面的程序说明了 *get()* 方法:
T3】程序 1:T5】

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the get() method

import java.time.OffsetTime;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the time
        OffsetTime time = OffsetTime.parse("15:30:30+07:00");

        // gets the time
        System.out.println(time.get(ChronoField.CLOCK_HOUR_OF_DAY));
    }
}
```

**Output:** 

```java
15
```