# Java 中的 ThaiBuddhistChronology eraOf()方法，示例

> 原文:[https://www . geeksforgeeks . org/thaibudhistderor-eraof-method-in-Java-with-example/](https://www.geeksforgeeks.org/thaibuddhistchronology-eraof-method-in-java-with-example/)

**Java . time . chrono . thaibudhistory**类的 **eraOf()** 方法用于使用数值检索 ThaiBuddhistEra。

**语法:**

```
public ThaiBuddhistEra eraOf(int eraValue)
```

**参数**:该方法将**整数值**作为将要生成 ThaiBuddhistEra 的参数。

**返回值:**该方法使用数值返回**泰国历史时代**。

以下是举例说明 **eraOf()** 方法的例子:

**例 1:**

```
// Java program to demonstrate
// eraOf() method

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
            // used in LocalDate
            ThaiBuddhistChronology crono
                = hidate.getChronology();

            // getting ThaiBuddhistEra for the
            // given integer value
            // by using eraOf() method
            ThaiBuddhistEra era = crono.eraOf(0);

            // display the result
            System.out.println(
                "ThaiBuddhistEra is: "
                + era);
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
// eraOf() method

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
            // used in LocalDate
            ThaiBuddhistChronology crono
                = hidate.getChronology();

            // getting ThaiBuddhistEra for the
            // given integer value
            // by using eraOf() method
            ThaiBuddhistEra era = crono.eraOf(1);

            // display the result
            System.out.println(
                "ThaiBuddhistEra is: "
                + era);
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
ThaiBuddhistEra is: BE

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibudhistechrome . html # eraOf-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistChronology.html#eraOf-int-)