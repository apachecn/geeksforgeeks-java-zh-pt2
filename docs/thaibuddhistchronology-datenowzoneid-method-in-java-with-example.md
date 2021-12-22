# Java 中的 thaibudhistechronous date now(ZoneId)方法，示例

> 原文:[https://www . geeksforgeeks . org/thaibudhistechr-datenowzoneid-method-in-Java-with-example/](https://www.geeksforgeeks.org/thaibuddhistchronology-datenowzoneid-method-in-java-with-example/)

**Java . time . chrono . thaibudhistory**类的 **dateNow()** 方法用于从指定时区的系统时钟中根据 thaibudhist 日历系统获取当前 thaibudhist。

**语法:**

```
public ThaiBuddhistDate dateNow(ZoneId zone)
```

**参数**:该方法以 id 区的**对象为参数。**

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

            // creating and initializing ZoneId object
            ZoneId id = ZoneId.systemDefault();

            // getting ThaiBuddhistDate for the
            // given zoneid object
            // by using dateNow() method
            ThaiBuddhistDate date = crono.dateNow(id);

            // display the result
            System.out.println("ThaiBuddhistDate is: "
                               + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
ThaiBuddhistDate is: ThaiBuddhist BE 2563-04-19

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

            // creating and initializing ZoneId object
            ZoneId id = ZoneId.of("Europe/Paris");

            // getting ThaiBuddhistDate for the
            // given zoneid object
            // by using dateNow() method
            ThaiBuddhistDate date = crono.dateNow(id);

            // display the result
            System.out.println("ThaiBuddhistDate is: "
                               + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
ThaiBuddhistDate is: ThaiBuddhist BE 2563-04-19

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibudhistorager . html # dateNow-Java . time . zoneid-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistChronology.html#dateNow-java.time.ZoneId-)