# Java 中的 YearMonth withYear()方法，带示例

> 原文:[https://www . geesforgeks . org/year-month-with year-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-withyear-method-in-java-with-examples/)

**with Year(int year)****YearMonth**类的方法，用于使用作为参数传递的 year 来更改 YearMonth 对象的年份，然后该方法返回更改后的 year month 的副本。此实例是不可变的，不受此方法调用的影响。

**语法:**

```java
public YearMonth withYear(int year)

```

**参数:**该方法接受**月**作为参数，该参数是返回的年-月中要设置的年份，从 MIN_YEAR 到 MAX_YEAR。

**返回值:**该方法返回一个基于该年-月的年-月和请求的年。

**异常:**如果年份值无效，此方法抛出**日期时间异常**。

下面的程序说明了 withYear()方法:
**程序 1:**

```java
// Java program to demonstrate
// YearMonth.withYear() method

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

        // apply withYear method of YearMonth class
        YearMonth updatedlocal = yr.withYear(2023);

        // print instance
        System.out.println("YearMonth after"
                           + " applying method: "
                           + updatedlocal);
    }
}
```

**Output:**

```java
YearMonth before applying method: 2019-12
YearMonth after applying method: 2023-12

```

**程序 2:**

```java
// Java program to demonstrate
// YearMonth.withYear() method

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

        // apply withYear method of YearMonth class
        YearMonth updatedlocal = yr.withYear(1992);

        // print instance
        System.out.println("YearMonth after"
                           + " applying method: "
                           + updatedlocal);
    }
}
```

**Output:**

```java
YearMonth before applying method: 2022-07
YearMonth after applying method: 1992-07

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html # with year(int)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#withYear(int))