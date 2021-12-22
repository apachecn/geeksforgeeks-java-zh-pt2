# Java 中的 YearMonth withMonth()方法，带示例

> 原文:[https://www . geesforgeks . org/year month-with month-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-withmonth-method-in-java-with-examples/)

**with Month(int month)****YearMonth**类的方法，用于使用作为参数传递的 month 来更改 YearMonth 对象的年中月份，然后该方法返回更改后的 year month 的副本。如果某月某日对于指定月份无效，则该日将被调整为该月的最后一个有效日期。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public YearMonth withMonth(int month)

```

**参数:**该方法接受**月**作为参数，该参数是返回的年-月中设置的月份，从 1 月 1 日到 12 月 12 日。

**返回值:**该方法返回一个基于该年-月的年-月和请求的月。

**异常:**如果年月值无效，该方法抛出**日期时间异常**。

下面的程序说明了 withMonth()方法:
**程序 1:**

```
// Java program to demonstrate
// YearMonth.withMonth() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a YearMonth object
        YearMonth yr
            = YearMonth.of(2019, 12);

        // print instance
        System.out.println("YearMonth before"
                           + " applying method: "
                           + yr);

        // apply withMonth method of YearMonth class
        YearMonth updatedlocal = yr.withMonth(1);

        // print instance
        System.out.println("YearMonth after"
                           + " applying method: "
                           + updatedlocal);
    }
}
```

**Output:**

```
YearMonth before applying method: 2019-12
YearMonth after applying method: 2019-01

```

**程序 2:**

```
// Java program to demonstrate
// YearMonth.withMonth() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a YearMonth object
        YearMonth yr
            = YearMonth.of(2022, 7);

        // print instance
        System.out.println("YearMonth before"
                           + " applying method: "
                           + yr);

        // apply withMonth method of YearMonth class
        YearMonth updatedlocal = yr.withMonth(12);

        // print instance
        System.out.println("YearMonth after"
                           + " applying method: "
                           + updatedlocal);
    }
}
```

**Output:**

```
YearMonth before applying method: 2022-07
YearMonth after applying method: 2022-12

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html # with month(int)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#withMonth(int))