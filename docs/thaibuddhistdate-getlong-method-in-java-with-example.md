# Java 中的 ThaiBuddhistDate getLong()方法，示例

> 原文:[https://www . geeksforgeeks . org/thaibudhistate-getlong-method-in-Java-with-example/](https://www.geeksforgeeks.org/thaibuddhistdate-getlong-method-in-java-with-example/)

类的 **getLong()** 方法用于以长格式检索传递的时态字段。

**语法:**

```
public long getLong(TemporalField field)
```

**参数:**该方法以任意类型的**时间场**为参数。

**返回值:**该方法以长格式返回传递的时态字段。

以下是说明 **getLong()** 方法的例子:

**例 1:**

```
// Java program to demonstrate
// getLong() method

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

            // Getting temporal field in long format
            // by using getLong() method
            long tempo
                = hidate.getLong(
                    ChronoField.EPOCH_DAY);

            // Display the result
            System.out.println(
                "Specified temporal field"
                + "in long format: "
                + tempo);
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
Specified temporal fieldin long format: 18385

```

**例 2:**

```
// Java program to demonstrate
// getLong() method

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

            // Getting temporal field in long format
            // by using getLong() method
            long tempo
                = hidate.getLong(
                    ChronoField.DAY_OF_WEEK);

            // Display the result
            System.out.println(
                "Specified temporal field"
                + "in long format: "
                + tempo);
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
Specified temporal fieldin long format: 7

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibudhistate . html # getLong-Java . time . temporal field-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistDate.html#getLong-java.time.temporal.TemporalField-)