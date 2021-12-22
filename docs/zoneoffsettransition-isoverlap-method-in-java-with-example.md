# Java 中的 ZoneOffsetTransition isOverlap()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransition-isoverlap-method-in-Java-with-example/](https://www.geeksforgeeks.org/zoneoffsettransition-isoverlap-method-in-java-with-example/)

类的 **isOverlap()** 方法用于检查转换之间是否有重叠。

**语法:**

```java
public boolean isOverlap()
```

**参数:**该方法不接受任何参数。

**返回值:**如果过渡之间有无重叠，该方法返回真。

以下是说明**等重叠()**方法的例子:

**例 1:**

```java
// Java program to demonstrate
// isOverlap() method

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
        boolean status = zonetrans1.isOverlap();

        // display the result
        if (status)
            System.out.println(
                "there is an overlapping");
        else
            System.out.println(
                "no overlapping found");
    }
}
```

**输出:**

```java
there is an overlapping

```

**例 2:**

```java
// Java program to demonstrate
// isOverlap() method

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
        boolean status = zonetrans1.isOverlap();

        // display the result
        if (status)
            System.out.println(
                "there is an overlapping");
        else
            System.out.println(
                "no overlapping found");
    }
}
```

**输出:**

```java
no overlapping found

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/zoneoffsettransition . html # isOverlap–](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransition.html#isOverlap--)