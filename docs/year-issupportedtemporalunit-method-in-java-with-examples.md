# Java 中的年发行支持(临时)方法，示例

> 原文:[https://www . geesforgeks . org/year-issupportedtemporalunit-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-issupportedtemporalunit-method-in-java-with-examples/)

**年**类的**isSupported(TemporalUnit)**方法用于检查年类是否支持指定的 TemporalUnit。实际上，这个方法检查我们今年是否可以使用传递的单位对指定的单位应用加法或减法运算。如果为 false，则调用加号(long，TemporalUnit)和减号方法将引发异常。

支持的计时单位是:

*   年
*   数十年
*   世纪
*   一千年
*   年代

所有其他计时单位实例将返回 false。

**语法:**

```
public boolean isSupported(TemporalUnit unit)

```

**参数:**该方法只接受一个代表时间单位的参数**单位**进行检查。

**返回值:**如果本年度支持单位，则该方法返回布尔值 true，否则返回 false。

以下程序说明了问题支持(临时)方法:

**程序 1:**

```
// Java program to demonstrate
// Year.isSupported(TemporalUnit) method

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
                ChronoUnit.YEARS);

        // print result
        System.out.println("YEARS unit is supported by Year class: "
                           + value);
    }
}
```

**Output:**

```
Year :2019
YEARS unit is supported by Year class: true

```

**程序 2:**

```
// Java program to demonstrate
// Year.isSupported(TemporalUnit) method

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
                ChronoUnit.MILLENNIA);

        // print result
        System.out.println("MILLENNIA unit is supported: "
                           + value);
    }
}
```

**Output:**

```
Year :2022
MILLENNIA unit is supported: true

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/year . html # isSupported(Java . time . temporalunit)](https://docs.oracle.com/javase/10/docs/api/java/time/Year.html#isSupported(java.time.temporal.TemporaUnit))