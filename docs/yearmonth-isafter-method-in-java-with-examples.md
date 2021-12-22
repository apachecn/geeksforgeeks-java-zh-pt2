# Java 中的 YearMonth isAfter()方法，示例

> 原文:[https://www . geesforgeks . org/year month-is after-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-isafter-method-in-java-with-examples/)

Java 中 **Year 类的**isaafter()**方法用于检查当前的 YearMonth 对象是否在作为该方法参数指定的 YearMonth 之后。**

**语法** :

```java
public boolean isAfter(Year otherYearMonth)

```

**参数**:接受单个参数 ***otherYearMonth*** ，与当前 YearMonth 对象进行比较。

**返回值**:如果这个 YearMonth 对象的值在作为方法参数指定的 YearMonth 对象的值之后，则返回一个**布尔值** True 值，否则返回 False。

下面的程序说明了 Java 中的 YearMonth.isAfter()方法:

**节目 1** :

```java
// Program to illustrate the isAfter() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create first Year object
        YearMonth yearMonth1
            = YearMonth.of(2018, 3);

        // Create second Year object
        YearMonth yearMonth2
            = YearMonth.of(1997, 4);

        // Check if this year-month object's value is
        // after the specified Year-month or not
        System.out.println(yearMonth1
                               .isAfter(yearMonth2));
    }
}
```

**节目 2** :

```java
// Program to illustrate the isAfter() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create first Year object
        YearMonth yearMonth1
            = YearMonth.of(1997, 3);

        // Create second Year object
        YearMonth yearMonth2
            = YearMonth.of(2018, 4);

        // Check if this year-month object's value is
        // after the specified Year-month or not
        System.out.println(yearMonth1
                               .isAfter(yearMonth2));
    }
}
```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year month . html # isaafter-Java . time . year month-](https://docs.oracle.com/javase/8/docs/api/java/time/YearMonth.html#isAfter-java.time.YearMonth-)