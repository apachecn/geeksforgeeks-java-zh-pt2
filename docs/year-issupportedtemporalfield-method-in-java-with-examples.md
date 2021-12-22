# Java 中的年发行支持(临时字段)方法，示例

> 原文:[https://www . geeksforgeeks . org/year-issupportedtemporalfield-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-issupportedtemporalfield-method-in-java-with-examples/)

**Year** 类的**isSupported(temporal field)**方法用于检查 Year 类是否支持指定的字段，这意味着使用该方法我们可以检查指定字段是否可以查询到 Year 对象。

计时场支持的字段有:

*   纪元年
*   年
*   时代

所有其他时间域实例都将返回 false。

**语法:**

```java
public boolean isSupported(TemporalField field)
```

**参数:**该方法只接受一个代表要检查字段的参数字段。
**返回值:**如果该字段在今年支持，则该方法返回布尔值 true，否则返回 false。

以下程序说明了问题支持(临时字段)方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Year.isSupported(TemporalField) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a Year object
        Year year = Year.of(2019);

        // print instance
        System.out.println("Year :"
                           + year);

        // apply isSupported() method
        boolean value
            = year.isSupported(
                ChronoField.YEAR_OF_ERA);

        // print result
        System.out.println("YEAR_OF_ERA Field is supported by Year class: "
                           + value);
    }
}
```

**输出**

```java
Year :2019
YEAR_OF_ERA Field is supported by Year class: true
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Year.isSupported(TemporalField) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a Year object
        Year year = Year.of(2022);

        // print instance
        System.out.println("Year :"
                           + year);

        // apply isSupported() method
        boolean value
            = year.isSupported(
                ChronoField.MILLI_OF_SECOND);

        // print result
        System.out.println("MilliSecond Field is supported: "
                           + value);
    }
}
```

**Output**

```java
Year :2022
MilliSecond Field is supported: false
```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/year . html # isSupported(Java . time . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/Year.html#isSupported(java.time.temporal.TemporalField))