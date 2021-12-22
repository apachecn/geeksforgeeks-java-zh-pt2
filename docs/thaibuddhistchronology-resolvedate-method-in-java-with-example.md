# Java 中的 ThaiBuddhistChronology resolveDate()方法，示例

> 原文:[https://www . geeksforgeeks . org/thaibudhistechr-resolved ate-method-in-Java-with-example/](https://www.geeksforgeeks.org/thaibuddhistchronology-resolvedate-method-in-java-with-example/)

**Java . time . chrono . thaibudhistory**类的**resolved date()**方法用于根据 thaibudhistory 日历，通过在特定解析器样式的帮助下解析与地图中特定长值相关联的时间字段来检索 thaibudhistory 日期。

**语法:**

```
public ThaiBuddhistDate resolveDate(
       Map fieldValues,
       ResolverStyle resolverStyle)

```

**参数:**该方法将以下参数作为参数:

*   **Field value:** This will contain the timing field.
*   **Parser Style:** This will parse the time field and provide the date.

**返回值:**该方法通过在特定解析器样式的帮助下解析与地图中特定长值相关联的 Chrono 字段，根据 ThaiBuddhist 日历返回本地日期。

以下示例说明了 **resolveDate()** 方法:

**例 1:**

```
// Java program to demonstrate
// resolveDate() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;
import java.time.format.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate
                = ThaiBuddhistDate.now();

            // getting  ThaiBuddhistChronology
            // used in  ThaiBuddhistDate
            ThaiBuddhistChronology crono
                = hidate.getChronology();

            // creating and initializing HashMap
            HashMap<TemporalField, Long> map
                = new HashMap<TemporalField, Long>();

            // putting element into HashMap
            map.put((TemporalField)
                        ChronoField.EPOCH_DAY,
                    30l);

            // getting the resolveDate with
            // SMART ResolverStyle
            // by using resolveDate() method
            hidate
                = crono.resolveDate(
                    map,
                    ResolverStyle.LENIENT);

            // display the result
            System.out.println("ThaiBuddhistDate is : "
                               + hidate);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**输出:**

```
ThaiBuddhistDate is : ThaiBuddhist BE 2513-01-31

```

**例 2:**

```
// Java program to demonstrate
// resolveDate() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;
import java.time.format.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate
                = ThaiBuddhistDate.now();

            // getting  ThaiBuddhistChronology
            // used in  ThaiBuddhistDate
            ThaiBuddhistChronology crono
                = hidate.getChronology();

            // creating and initializing HashMap
            HashMap<TemporalField, Long> map
                = new HashMap<TemporalField, Long>();

            // putting element into HashMap
            map.put((TemporalField)
                        ChronoField.HOUR_OF_AMPM,
                    30l);

            // getting the resolveDate with
            // SMART ResolverStyle
            // by using resolveDate() method
            hidate
                = crono.resolveDate(
                    map,
                    ResolverStyle.LENIENT);

            // display the result
            System.out.println("ThaiBuddhistDate is : "
                               + hidate);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**输出:**

```
ThaiBuddhistDate is : null

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibudhistechrome . html # resolved ate-Java . util . map-Java . time . format . resolver style-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistChronology.html#resolveDate-java.util.Map-java.time.format.ResolverStyle-)