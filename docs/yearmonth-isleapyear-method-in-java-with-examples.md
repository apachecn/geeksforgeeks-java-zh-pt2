# year month is apy ear()方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/year month-islapyear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-isleapyear-method-in-java-with-examples/)

Java 中 **YearMonth 类**的**islapyear()**方法是用来检查这个 YearMonth 对象中的年份是否为闰年。

根据无产历系统规则，如果一年能被 4 整除，那么它就是闰年。

*   Not divisible by 100, but divisible by 400.

**语法** :

```java
public boolean isLeapYear()

```

**参数**:该方法不接受任何参数。

**返回值**:如果这个 YearMonth 对象中的年的值根据 proleptic calendar 系统规则是闰年，则返回**布尔值** True 值，否则返回 False。

下面的程序用 Java 说明了 YearMonth 的 isLeapYear()方法:

**程序 1** :

```java
// Program to illustrate the isLeap() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create YearMonth object
        YearMonth yearMonth = YearMonth.of(2016, 2);

        // Check if year in this YearMonth object's
        // value is a leap year or not
        System.out.println(yearMonth.isLeapYear());
    }
}
```

**输出:**

```java
true

```

**程序二** :

```java
// Program to illustrate the isLeap() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create YearMonth object
        YearMonth yearMonth = YearMonth.of(1990, 2);

        // Check if year in this YearMonth object's
        // value is a leap year or not
        System.out.println(yearMonth.isLeapYear());
    }
}
```

**输出:**

```java
false

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year month . html # IsLapyear–](https://docs.oracle.com/javase/8/docs/api/java/time/YearMonth.html#isLeap--)