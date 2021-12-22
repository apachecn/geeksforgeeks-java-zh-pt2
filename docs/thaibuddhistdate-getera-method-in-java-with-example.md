# Java 中的 ThaiBuddhistDate getEra()方法，示例

> 原文:[https://www . geeksforgeeks . org/thaibudhistate-getera-method-in-Java-with-example/](https://www.geeksforgeeks.org/thaibuddhistdate-getera-method-in-java-with-example/)

**Java . time . chrono . thaibudhistate**类的 **getEra()** 方法用于检索与该 thaibudhistate 日期相关的纪元。

**语法:**

```
public ThaiBuddhistEra getEra()
```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回这个 ThaiBuddhist 日期的纪元。

下面是举例说明 **getEra()** 方法的例子:

**例 1:**

```
// Java program to demonstrate
// getEra() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate
                = ThaiBuddhistDate.now();

            // Getting chronology of this date
            // by using getEra() method
            ThaiBuddhistEra crono
                = hidate.getEra();

            // Display the result
            System.out.println(
                "ThaiBuddhistEra: "
                + crono);
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
ThaiBuddhistEra: BE

```

**例 2:**

```
// Java program to demonstrate
// getEra() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate
                = ThaiBuddhistDate.of(2008, 04, 24);

            // Getting chronology of this date
            // by using getEra() method
            ThaiBuddhistEra crono
                = hidate.getEra();

            // Display the result
            System.out.println(
                "ThaiBuddhistEra: "
                + crono);
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
ThaiBuddhistEra: BE

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibuddhistdate . html # getEra–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistDate.html#getEra--)