# Java 中的 Year adjustInto()方法，带示例

> 原文:[https://www . geesforgeks . org/year-adjustin to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-adjustinto-method-in-java-with-examples/)

**adjustInto()** 方法的 **Year** 类用于调整传递的时态对象，使其具有应用该方法的年份。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public Temporal adjustInto(Temporal temporal)

```

**参数:**该方法接受**时间**作为参数，该参数是要调整的目标时间对象。它不应为空。

**返回值:**此方法返回调整后的对象。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果无法进行调整。
*   **算术异常**–如果出现数值溢出。

以下程序说明了 adjustInto()方法:
**程序 1:**

```
// Java program to demonstrate
// Year.adjustInto() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Year object
        Year yr
            = Year.of(2019);

        // create a temporal object
        LocalDate date = LocalDate.parse("2007-12-03");

        // print instance
        System.out.println("LocalDate :"
                           + date);

        // apply adjustInto method of Year class
        LocalDate updatedlocal = (LocalDate)yr.adjustInto(date);

        // print instance
        System.out.println("LocalDate after"
                           + " applying adjustInto method: "
                           + updatedlocal);
    }
}
```

**Output:**

```
LocalDate :2007-12-03
LocalDate after applying adjustInto method: 2019-12-03

```

**程序 2:**

```
// Java program to demonstrate
// Year.adjustInto() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a Year object
        Year yr
            = Year.of(2032);

        // create a temporal object
        LocalDate date = LocalDate.parse("2017-01-13");

        // print instance
        System.out.println("LocalDate :"
                           + date);

        // apply adjustInto method of Year class
        LocalDate updatedlocal = (LocalDate)yr.adjustInto(date);

        // print instance
        System.out.println("LocalDate after"
                           + " applying adjustInto method: "
                           + updatedlocal);
    }
}
```

**Output:**

```
LocalDate :2017-01-13
LocalDate after applying adjustInto method: 2032-01-13

```

**参考文献:**T2