# Java 中的 thaibudhistegraphy prolepiecialyear()方法，示例

> 原文:[https://www . geeksforgeeks . org/thaibudhistechr-prolepiecifyear-in-Java-method-with-example/](https://www.geeksforgeeks.org/thaibuddhistchronology-prolepticyear-method-in-java-with-example/)

**Java . time . chrono . thaibudhistory**类的**prolepiecialyear()**方法用于检索特定 thaibudhistr 时代的 thaibudhistr 系统中存在的 prolepiecialyear。

**语法:**

```
public int prolepticYear(
      Era era, int yearOfEra)

```

**参数**:该方法以下列参数为参数。

*   **Age:** That is, the object of the ThaiBuddhist era.
*   **yearofera:** is the year of a specific Thai historical era.

**返回值:**该方法返回特定泰国历史时代泰国历史系统中出现的**预测年**。

以下是说明**prolepiecialyear()**方法的示例:

**例 1:**

```
// Java program to demonstrate
// prolepticYear() method

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

            // getting prolepticYear for the
            // given year of Era
            // by using prolepticYear() method
            int proyear
                = crono.prolepticYear(
                    ThaiBuddhistEra.BE,
                    1444);

            // display the result
            System.out.println("proleptic Year is: "
                               + proyear);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
proleptic Year is: 1444

```

**例 2:**

```
// Java program to demonstrate
// prolepticYear() method

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

            // getting prolepticYear for the
            // given year of Era
            // by using prolepticYear() method
            int proyear
                = crono.prolepticYear(
                    ThaiBuddhistEra.BEFORE_BE,
                    1444);

            // display the result
            System.out.println("proleptic Year is: "
                               + proyear);
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
proleptic Year is: -1443

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibudhistechrome . html # prolepiecialyear-Java . time . chrono . era-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistChronology.html#prolepticYear-java.time.chrono.Era-int-)