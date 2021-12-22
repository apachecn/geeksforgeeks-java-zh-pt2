# Java 中的 thaibudhistechronic date year day(Era，int，int)方法

> 原文:[https://www . geeksforgeeks . org/thaibudhistderor-datyeardayera-int-int-method-in-Java/](https://www.geeksforgeeks.org/thaibuddhistchronology-dateyeardayera-int-int-method-in-java/)

**Java . time . chrono . thaibudhistory**类的 **dateYearDay()** 方法用于根据特定时代的 thaibudhistory 日历检索 thaibudhistory 日期。

**语法:**

```java
public ThaiBuddhistDate dateYearDay(
  Era era, int yearOfEra, int dayOfYear)

```

**参数**:该方法以下列参数为参数:

*   **时代:**哪个是类型时代的对象
*   **年:**是泰国历史上年份字段的整数优先年
*   **日:**是 ThaiBuddhistDate 的日字段的整数日

**返回值:**该方法根据特定年份和日期的泰国历返回**泰国历日期**。

**异常:**该方法抛出**日期时间异常**-如果给定的数据无法形成日期。

以下是举例说明 **dateYearDay()** 方法的例子:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// dateYearDay() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate
                = ThaiBuddhistDate.now();

            // getting ThaiBuddhistChronology
            // used in ThaiBuddhistDate
            ThaiBuddhistChronology crono
                = hidate.getChronology();

            // getting ThaiBuddhistDate for the
            // given date and year field
            // by using dateYearDay() method
            ThaiBuddhistDate date
                = crono.dateYearDay(
                    ThaiBuddhistEra.BE,
                    2018,
                    24);

            // display the result
            System.out.println(
                "ThaiBuddhistDate is: "
                + date);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can "
                + "not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**Output:**

```java
ThaiBuddhistDate is: ThaiBuddhist BE 2018-01-24

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// dateYearDay() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate
                = ThaiBuddhistDate.now();

            // getting ThaiBuddhistChronology
            // used in ThaiBuddhistDate
            ThaiBuddhistChronology crono
                = hidate.getChronology();

            // getting ThaiBuddhistDate for the
            // given date and year field
            // by using dateYearDay() method
            ThaiBuddhistDate date
                = crono.dateYearDay(
                    ThaiBuddhistEra.BEFORE_BE,
                    2018,
                    24);

            // display the result
            System.out.println(
                "ThaiBuddhistDate is: "
                + date);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can "
                + "not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**Output:**

```java
ThaiBuddhistDate is: ThaiBuddhist BEFORE_BE 2018-01-24

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibudhistechrome . html # datyearday-Java . time . chrono . era-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistChronology.html#dateYearDay-java.time.chrono.Era-int-int-)