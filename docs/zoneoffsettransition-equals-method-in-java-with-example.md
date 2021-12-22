# Java 中的 ZoneOffsetTransition equals()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransition-equals-method-in-Java-with-example/](https://www.geeksforgeeks.org/zoneoffsettransition-equals-method-in-java-with-example/)

**Java . time . ZoneOffsetTransition**类的 **equals()** 方法用于对 ZoneOffsetTransition 类型的两个对象进行比较。

**语法:**

```
public boolean equals(Object other)
```

**参数:**该方法以其他 zoneoffsetTransition 的对象为参数。

**返回值:**如果两个对象相等，该方法返回真，否则返回假。

以下是说明**等于()**方法的示例:

**例 1:**

```
// Java program to demonstrate
// equals() method

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
                1999, 04, 25, 03,
                24, 45, 0);

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

        // creating and initializing
        // ZoneOffsetTransition Object
        ZoneOffsetTransition zonetrans2
            = ZoneOffsetTransition.of(
                loc, off1, off2);

        // comparing both object using
        // equals() method
        boolean status
            = zonetrans1.equals(zonetrans2);

        // display the result
        if (status)
            System.out.println(
                "zonetrans1 is equal to zonetrans2");
        else
            System.out.println(
                "zonetrans1 is not equal to zonetrans2");
    }
}
```

**输出:**

```
zonetrans1 is equal to zonetrans2

```

**例 2:**

```
// Java program to demonstrate
// equals() method

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
                03, 24, 45, 0);

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

        // creating and initializing
        // ZoneOffsetTransition Object
        ZoneOffsetTransition zonetrans2
            = ZoneOffsetTransition
                  .of(LocalDateTime.of(
                          1999, 04, 25, 03,
                          24, 48, 0),
                      off1, off2);

        // comparing both object using
        // equals() method
        boolean status
            = zonetrans1.equals(zonetrans2);

        // display the result
        if (status)
            System.out.println(
                "zonetrans1 is equal to zonetrans2");
        else
            System.out.println(
                "zonetrans1 is not equal to zonetrans2");
    }
}
```

**输出:**

```
zonetrans1 is not equal to zonetrans2

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/zoneoffsettransition . html # equals-Java . lang . object-](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransition.html#equals-java.lang.Object-)