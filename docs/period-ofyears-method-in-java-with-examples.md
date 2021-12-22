# Java 中的 Period ofYears()方法，带示例

> 原文:[https://www . geesforgeks . org/period-of yers-in-Java-method-in-examples/](https://www.geeksforgeeks.org/period-ofyears-method-in-java-with-examples/)

**周期**类的**年(int number of yers)**方法用于从给定的年数中获取一个周期作为参数。获得的周期将代表年数。单位月和日应保持为 0。

**语法:**

```
public static Period ofYears(int numberOfYears)

```

**参数:**该方法接受代表年数的整数型单参数**年数**。它可以是消极的，也可以是积极的。

**返回值:**这个方法必须返回一个**周期**，代表年数。

**异常:**此方法不抛出任何异常。

下面的程序说明了 Java 中 Period 的 ofYears()方法:

**程序 1:**

```
// Java program to demonstrate
// Period ofYears(int numberOfYears) method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create Period object
        Period period
            = Period.ofYears(5);

        // Print period
        System.out.println("Years: "
                           + period.getYears());
        System.out.println("Months: "
                           + period.getMonths());
        System.out.println("Days: "
                           + period.getDays());
    }
}
```

**Output:**

```
Years: 5
Months: 0
Days: 0

```

**程序 2:**

```
// Java program to demonstrate
// Period ofYears(int numberOfYears) method
import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        int numberOfYears = -10;

        // Create Period object
        Period period
            = Period.ofYears(numberOfYears);

        // Print period
        System.out.println("Years: "
                           + period.getYears());
        System.out.println("Months: "
                           + period.getMonths());
        System.out.println("Days: "
                           + period.getDays());
    }
}
```

**Output:**

```
Years: -10
Months: 0
Days: 0

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/period . html # of yers(int)](https://docs.oracle.com/javase/10/docs/api/java/time/Period.html#ofYears(int))