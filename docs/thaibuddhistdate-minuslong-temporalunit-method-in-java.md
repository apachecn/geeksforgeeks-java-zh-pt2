# Java 中的 ThaiBuddhistDate 减(long，TemporalUnit)方法

> 原文:[https://www . geeksforgeeks . org/thaibudhistate-mins long-tempalalunit-method-in-Java/](https://www.geeksforgeeks.org/thaibuddhistdate-minuslong-temporalunit-method-in-java/)

**Java . time . chrono . thaibudhistate**类的**减()**方法用于在从当前 thaibudhistat 日期中减去一定数量的时态存取器单位后得到 thaibudhistat 日期。

**语法:**

```
public ThaiBuddhistDate minus(
           long amountToSubtract,
           TemporalUnit unit)
```

**参数:**该方法采用以下参数作为参数:

*   **amountToSubtract:** 这是要从当前 ThaiBuddhist 日期中减去的时间单位值。
*   **单位:**时间单位或时间单位的对象。

**返回值:**此方法在从当前 thaibudhist 日期中减去一个时间访问器单位后，返回 thaibudhist 日期。

以下是举例说明**减去()**方法的例子:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate minus() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate
                = ThaiBuddhistDate.now();

            // Display the result
            System.out.println(
                "Old ThaiBuddhist date: "
                + hidate);

            // Subtracting ThaiBuddhist date
            // by using minus() method
            ThaiBuddhistDate newdate
                = hidate.minus(
                    22, ChronoUnit.DAYS);

            // Display the result
            System.out.println(
                "New ThaiBuddhist date: "
                + newdate);
        }
        catch (DateTimeException e) {

            System.out.println(
                "Passed parameter can"
                + " not form a date");

            System.out.println(
                "Exception thrown: "
                + e);
        }
    }
}
```

**Output:** 

```
Old ThaiBuddhist date: ThaiBuddhist BE 2563-05-03
New ThaiBuddhist date: ThaiBuddhist BE 2563-04-11
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate minus() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate
                = ThaiBuddhistDate.now();

            // Display the result
            System.out.println(
                "Old ThaiBuddhist date: "
                + hidate);

            // Subtracting ThaiBuddhist date
            // by using minus() method
            ThaiBuddhistDate newdate
                = hidate.minus(
                    4, ChronoUnit.DECADES);

            // Display the result
            System.out.println(
                "New ThaiBuddhist date: "
                + newdate);
        }
        catch (DateTimeException e) {

            System.out.println(
                "Passed parameter can"
                + " not form a date");

            System.out.println(
                "Exception thrown: "
                + e);
        }
    }
}
```

**Output:** 

```
Old ThaiBuddhist date: ThaiBuddhist BE 2563-05-03
New ThaiBuddhist date: ThaiBuddhist BE 2523-05-03
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibudhistate . html #减-long-Java . time . temporalunit-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistDate.html#minus-long-java.time.temporal.TemporalUnit-)