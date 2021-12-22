# Java 中的 thaibudhistechronic date year day(int，int)方法，示例

> 原文:[https://www . geeksforgeeks . org/thaibudhistechr-datyear dayint-int-method-in-Java-with-example/](https://www.geeksforgeeks.org/thaibuddhistchronology-dateyeardayint-int-method-in-java-with-example/)

**Java . time . chrono . thaibudhistory**类的 **dateYearDay()** 方法用于根据特定年份和日期的 thaibudhistory 日历检索 thaibudhistory 日期。

**语法:**

```java
public ThaiBuddhisteDate dateYearDay(
  int prolepticYear, int dayOfYear)

```

**参数**:该方法以下列参数为参数:

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
                = crono.dateYearDay(2018, 24);

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
                = crono.dateYearDay(2018, -24);

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
passed parameter can not form a date
Exception thrown: java.time.DateTimeException: Invalid value for DayOfYear (valid values 1 - 365/366): -24

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibudhistechrome . html # datyearday-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistChronology.html#dateYearDay-int-int-)