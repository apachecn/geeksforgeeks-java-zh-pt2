# YearMonth now()方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/year month-now-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-now-method-in-java-with-examples/)

Java 中 **YearMonth** 类的 **now()** 方法用于从默认时区的系统时钟中获取当前的年-月。

**语法:**

```java
public static YearMonth now()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法使用系统时钟和默认时区返回当前**年-月**。

下面的程序说明了 Java 中 YearMonth 的 now()方法:

**程序 1:**

```java
// Java program to demonstrate
// YearMonth.now() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply now() method
        // of YearMonth class
        YearMonth result = YearMonth.now();

        // print both year and month
        System.out.println("YearMonth: "
                           + result);
    }
}
```

**输出:**

```java
YearMonth: 2020-05

```

**程序二:**

```java
// Java program to demonstrate
// YearMonth.now() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply now() method
        // of YearMonth class
        YearMonth result = YearMonth.now();

        // print only year
        System.out.println(
            "Year: "
            + result.get(ChronoField.YEAR));
    }
}
```

**输出:**

```java
Year: 2020

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html # now()](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#now())