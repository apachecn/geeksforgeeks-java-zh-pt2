# Java 中的 thaibudhistory date(int，int，int)方法

> 原文:[https://www . geeksforgeeks . org/thaibudhistechr-dateint-int-int-method-in-Java/](https://www.geeksforgeeks.org/thaibuddhistchronology-dateint-int-int-method-in-java/)

**Java . time . chrono . ThaiBuddhist**类的 **date()** 方法用于根据 thaibudhistory 系统获取给定年、月、日的本地日期。
**语法:**

```java
public ThaiBuddhistDate date(int prolepticYear,
                         int month,
                         int dayOfMonth)
```

**参数**:该方法以下列参数为参数。

*   **预测年:**泰国年份字段的整数预测年
*   **月:**thaibudhist 月字段的整数月
*   **日:**thaibudhist 日字段的整数日

**返回值:**该方法根据泰国佛历系统返回给定年、月、日的**泰国历**。
**异常:**如果给定的日、月、年字段无法形成结构化日期，该方法抛出**日期时间异常**。
以下举例说明**日期()**方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// date() method

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
            ThaiBuddhistDate lodate
                = ThaiBuddhistDate.now();

            // getting ThaiBuddhistChronology
            // used in ThaiBuddhistDate
            ThaiBuddhistChronology crono
                = lodate.getChronology();

            // getting ThaiBuddhistDate for the
            // given date, month and year field
            // by using date() method
            ThaiBuddhistDate date
                = crono.date(2018, 05, 24);

            // display the result
            System.out.println(
                "ThaiBuddhistDate is: "
                + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can "
                               + "not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output:** 

```java
ThaiBuddhistDate is: ThaiBuddhist BE 2018-05-24
```