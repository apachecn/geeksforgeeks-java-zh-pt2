# Java 中的 ThaiBuddhistChronology dateNow(时钟)方法，示例

> 原文:[https://www . geeksforgeeks . org/thaibudhistechro-datenowclock-in-Java-method-with-example/](https://www.geeksforgeeks.org/thaibuddhistchronology-datenowclock-method-in-java-with-example/)

**Java . time . chrono . thaibudhistory**类的 **dateNow()** 方法用于从指定的时钟对象中根据 thaibudhist 日历系统获取当前的 thaibudhistory 日期。

**语法:**

```
public ThaiBuddhistDate dateNow(Clock clock)
```

**参数**:该方法以**时钟**的对象为参数，用于从指定的时钟对象中根据泰国历系统获取当前泰国历日期。

**返回值:**该方法从指定的时钟对象根据 thaibudhist 日历系统返回 thaibudhist 日期。

以下是举例说明 **dateNow()** 方法的例子:

**例 1:**

```
// Java program to demonstrate
// dateNow() method

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

            // creating and initializing
            // clock object
            Clock clock = Clock.systemUTC();

            // getting ThaiBuddhistDate for the
            // given clock object
            // by using dateNow() method
            ThaiBuddhistDate date
                = crono.dateNow(clock);

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

**输出:**

```
JapaneseDate is: Japanese Heisei 32-03-11

```

**例 2:**

```
// Java program to demonstrate
// dateNow() method

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

            // creating and initializing
            // clock object
            Clock clock = Clock.systemUTC();

            // setting clock
            clock = Clock.tick(
                clock,
                Duration.ofDays(100));

            // getting ThaiBuddhistDate for the
            // given clock object
            // by using dateNow() method
            ThaiBuddhistDate date
                = crono.dateNow(clock);

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

**输出:**

```
ThaiBuddhistDate is: ThaiBuddhist BE 2563-02-08

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibudhistorager . html # dateNow-Java . time . clock-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistChronology.html#dateNow-java.time.Clock-)