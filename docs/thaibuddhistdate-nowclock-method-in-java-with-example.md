# Java 中的 ThaiBuddhistDate now(时钟)方法，示例

> 原文:[https://www . geeksforgeeks . org/thaibudhistdata-now clock-in-Java-method-with-example/](https://www.geeksforgeeks.org/thaibuddhistdate-nowclock-method-in-java-with-example/)

**Java . time . chrono . thaibudhistate**类的 **now()** 方法用于根据 thaibudhist 日历系统从指定的时钟获取当前的 thaibudhist 日期。

**语法:**

```
public static ThaiBuddhistDate
              now(Clock clock)

```

**参数:**该方法以**时钟**为对象，在此基础上形成时间表。

**返回值:**该方法根据指定时钟的 thaibudhist 日历系统返回当前 thaibudhist 日期。

以下是举例说明**现在()**方法的例子:

**例 1:**

```
// Java program to demonstrate now() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing clock
            Clock clock
                = Clock.systemUTC();

            // Creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate
                = ThaiBuddhistDate.now(clock);

            // Display the result
            System.out.println(
                "ThaiBuddhistDate: "
                + hidate);
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

**输出:**

```
ThaiBuddhistDate: ThaiBuddhist BE 2563-05-03

```

**例 2:**

```
// Java program to demonstrate now() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing clock
            Clock clock
                = Clock.systemDefaultZone();

            // Creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate
                = ThaiBuddhistDate.now(clock);

            // Display the result
            System.out.println(
                "ThaiBuddhistDate: "
                + hidate);
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

**输出:**

```
ThaiBuddhistDate: ThaiBuddhist BE 2563-05-03

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibudhistate . html # now-Java . time . clock-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistDate.html#now-java.time.Clock-)