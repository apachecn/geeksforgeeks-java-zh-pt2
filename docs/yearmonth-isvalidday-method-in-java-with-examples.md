# YearMonth 是 Java 中的 isValidDay()方法，示例

> 原文:[https://www . geesforgeks . org/year month-is validay-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-isvalidday-method-in-java-with-examples/)

Java 中 **YearMonth 类的**is validay()**方法用于检查这个 YearMonth 对象和作为该方法的参数提供的整数所表示的月-日是否可以一起构成有效日期。**

**语法** :

```
public boolean isValidDay(int monthDay)

```

**参数**:此方法接受单个参数 ***月日*** ，表示需要用此 YearMonth 对象检查的月日。

**返回值**:如果这个 YearMonth 对象和以整数表示的给定的月-日可以组成一个有效的日期，则返回一个**布尔值** True 值，否则返回 False。

下面的程序说明了 Java 中的 year month . is validay()方法:

**程序 1** :

```
// Program to illustrate the isValidDay() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create YearMonth object
        YearMonth yearMonth = YearMonth.of(2016, 2);

        // Check if the day passed is valid
        System.out.println(yearMonth.isValidDay(24));
    }
}
```

**输出:**

```
true

```

**方案二**:下面的方案中，年份是指 1990 年，不是闰年，月日代表闰年。因此，它们不能一起形成有效的日期，因此该方法将返回 false。

```
// Program to illustrate the isValidDay() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Create YearMonth object
        YearMonth yearMonth = YearMonth.of(1990, 2);

        // Check if the day passed is valid
        System.out.println(yearMonth.isValidDay(29));
    }
}
```

**输出:**

```
false

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/year month . html # isvaliday-Java . time . monthday-](https://docs.oracle.com/javase/8/docs/api/java/time/Year.html#isValidMonthDay-java.time.MonthDay-)