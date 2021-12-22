# Java 中的 ThaiBuddhistChronology()方法，示例

> 原文:[https://www . geeksforgeeks . org/thaibudhistechr-eras-method-in-Java-with-example/](https://www.geeksforgeeks.org/thaibuddhistchronology-eras-method-in-java-with-example/)

**Java . time . chrono . ThaiBuddhist**类的**纪元()**方法用于检索该特定 thaibudhistory 年表下的所有纪元。

**语法:**

```
public List eras()
```

**参数:**此方法不接受任何参数作为参数。

**返回值:**该方法返回该特定 ThaiBuddhist 年表下的所有年代。

以下是说明**纪元()**方法的示例:

**例 1:**

```
// Java program to demonstrate
// eras() method

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

            // getting all ThaiBuddhistEras present
            // by using eraOf() method
            List<Era> list = crono.eras();

            // display the result
            System.out.println(
                "ThaiBuddhistEra is: "
                + (list.iterator()).next());
        }
        catch (DateTimeException e) {
            System.out.println(
                "ThaiBuddhistEra is invalid");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
ThaiBuddhistEra is: BEFORE_BE

```

**例 2:**

```
// Java program to demonstrate
// eras() method

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

            // getting all ThaiBuddhistEras present
            // by using eraOf() method
            List<Era> list = crono.eras();

            // getting list Iterator
            Iterator iter = list.iterator();

            // display the result
            System.out.println("List of ThaiBuddhistEra : ");
            for (int i = 0; i < 2; i++)
                System.out.println(iter.next());
        }
        catch (DateTimeException e) {
            System.out.println(
                "MinguoEra is invalid");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
List of ThaiBuddhistEra : 
BEFORE_BE
BE

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibudhistechrome . html # eras–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistChronology.html#eras--)