# Java 中的 thaibudhistechrometry date epochday()方法，示例

> 原文:[https://www . geeksforgeeks . org/thaibudhistechr-datepochday-method-in-Java-with-example/](https://www.geeksforgeeks.org/thaibuddhistchronology-dateepochday-method-in-java-with-example/)

**Java . time . chrono . ThaiBuddhist**类的 **dateEpochDay()** 方法用于根据 thaibudhistory 日历系统从大纪元日获取本地日期。
**语法:**

```java
public ThaiBuddhistDate dateEpochDay(long epochDay)
```

**参数**:该方法以 long 类型的 epochDay 为参数。
**返回值:**此方法根据泰国历系统从大纪元日返回当地日期。
**异常:**如果给定的纪元日无法形成结构化日期，该方法抛出**日期时间异常**。
以下是举例说明**datepochday()**方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// dateEpochDay() method

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

            // display the result
            System.out.println("current ThaiBuddhistDate is: "
                               + hidate);

            // getting ThaiBuddhistDate for the
            // given TemporalAccessor object
            // by using date() method
            hidate = crono.dateEpochDay(23456);

            // display the result
            System.out.println("\nThaiBuddhistDate(according "
                               + "to ephochday) is: "
                               + hidate);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output**

```java
current ThaiBuddhistDate is: ThaiBuddhist BE 2564-06-25

ThaiBuddhistDate(according to ephochday) is: ThaiBuddhist BE 2577-03-22

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// dateEpochDay() method

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

            // display the result
            System.out.println("current ThaiBuddhistDate is: "
                               + hidate);

            // getting ThaiBuddhistDate for the
            // given TemporalAccessor object
            // by using date() method
            hidate = crono.dateEpochDay(-99999999);

            // display the result
            System.out.println("\nThaiBuddhistDate(according "
                               + "to ephochday) is: "
                               + hidate);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output**

```java
current ThaiBuddhistDate is: ThaiBuddhist BE 2564-06-25

ThaiBuddhistDate(according to ephochday) is: ThaiBuddhist BEFORE_BE 271279-04-21

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibudhistorager . html # dateepchtday-long-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistChronology.html#dateEpochDay-long-)