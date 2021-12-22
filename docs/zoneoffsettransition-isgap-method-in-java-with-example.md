# Java 中的 ZoneOffsetTransition isGap()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransition-isgap-method-in-Java-with-example/](https://www.geeksforgeeks.org/zoneoffsettransition-isgap-method-in-java-with-example/)

**Java . time . zone . OffsetTransition**类的 **isGap()** 方法用于检查该区域 offset transition 所代表的本地时间是否有间隙。

**语法:**

```
public boolean isGap()
```

**参数:**该方法不接受任何参数。

**返回值:**如果过渡中有间隙，该方法返回真，否则返回假。

以下是说明 **isGap()** 方法的例子:

**例 1:**

```
// Java program to demonstrate
// isGap() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.zone.*;

public class GFG {
    public static void main(String[] argv)
    {

        // creating and initializing
        // the object of LocalDateTime
        LocalDateTime loc
            = LocalDateTime.of(
                1999, 04, 25,
                03, 24, 59, 0);

        // creating and initializing
        // the object of ZoneOffset
        ZoneOffset off1
            = ZoneOffset.ofHoursMinutes(0, 8);

        // creating and initializing
        // the object of ZoneOffset
        ZoneOffset off2
            = ZoneOffset.ofTotalSeconds(9);

        // creating and initializing
        // ZoneOffsetTransition Object
        ZoneOffsetTransition zonetrans1
            = ZoneOffsetTransition.of(
                loc, off1, off2);

        // comparing both object using
        // equals() method
        boolean status = zonetrans1.isGap();

        // display the result
        if (status)
            System.out.println("there is a gap");
        else
            System.out.println("no gap found");
    }
}
```

**输出:**

```
no gap found

```

**例 2:**

```
// Java program to demonstrate
// isGap() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.zone.*;

public class GFG {
    public static void main(String[] argv)
    {

        // creating and initializing
        // the object of LocalDateTime
        LocalDateTime loc
            = LocalDateTime.of(
                1999, 04, 25,
                03, 24, 59, 0);

        // creating and initializing
        // the object of ZoneOffset
        ZoneOffset off1
            = ZoneOffset.ofTotalSeconds(8);

        // creating and initializing
        // the object of ZoneOffset
        ZoneOffset off2
            = ZoneOffset.ofTotalSeconds(12);

        // creating and initializing
        // ZoneOffsetTransition Object
        ZoneOffsetTransition zonetrans1
            = ZoneOffsetTransition.of(
                loc, off1, off2);

        // comparing both object using
        // equals() method
        boolean status = zonetrans1.isGap();

        // display the result
        if (status)
            System.out.println("there is a gap");
        else
            System.out.println("no gap found");
    }
}
```

**输出:**

```
there is a gap

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/zoneoffsettransition . html # isGap–](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransition.html#isGap--)