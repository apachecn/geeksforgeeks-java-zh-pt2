# 年月现(区)用 Java 举例

> 原文:[https://www . geesforgeks . org/year month-now zone-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-nowzone-in-java-with-examples/)

**现在(ZoneId zone)**Java 中 **YearMonth** 类的方法用于从指定时区的系统时钟中获取当前的年-月。
**语法:**

```
public static YearMonth now(ZoneId zone)
```

**参数:**此方法接受**月添加**作为代表要使用的区域标识的参数。

**返回值:**该方法使用系统时钟返回当前的年-月。

下面的程序说明了 Java 中的 YearMonth 的 now(ZoneId 区域)方法:

**程序 1:**

```
// Java program to demonstrate
// YearMonth.now(ZoneId zone) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply now(ZoneId zone) method
        // of YearMonth class
        YearMonth result
            = YearMonth.now(
                ZoneId.systemDefault());

        // print both year and month
        System.out.println("YearMonth: "
                           + result);
    }
}
```

**Output:**

```
YearMonth: 2020-05

```

**程序 2:**

```
// Java program to demonstrate
// YearMonth.now(ZoneId zone) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply now(ZoneId zone) method
        // of YearMonth class
        YearMonth result
            = YearMonth.now(
                ZoneId.systemDefault());

        // print only year
        System.out.println(
            "Year: "
            + result.get(
                  ChronoField.YEAR));
    }
}
```

**Output:**

```
Year: 2020

```

**程序 3:**

```
// Java program to demonstrate
// YearMonth.now(ZoneId zone) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply now(ZoneId zone) method
        // of YearMonth class
        YearMonth result
            = YearMonth.now(
                ZoneId.systemDefault());

        // print only month
        System.out.println(
            "Month: "
            + result.get(
                  ChronoField.MONTH_OF_YEAR));
    }
}
```

**Output:**

```
Month: 5

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html # now(Java . time . zoneid)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#now(java.time.ZoneId))