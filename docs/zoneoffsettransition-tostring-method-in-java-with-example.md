# Java 中的 ZoneOffsetTransition toString()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransition-tostring-method-in-Java-with-example/](https://www.geeksforgeeks.org/zoneoffsettransition-tostring-method-in-java-with-example/)

**Java . time . zone . zoneoffsettransition**类的 **toString()** 方法用于获取该特定区域偏移转换对象的字符串表示。

**语法:**

```
public String toString()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回该特定区域偏移转换的字符串表示。

以下是说明 **toString()** 方法的示例:

**示例 1:**

```
// Java program to demonstrate
// toString() method

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
            = ZoneOffset.ofTotalSeconds(12);

        // creating and initializing
        // the object of ZoneOffset
        ZoneOffset off2
            = ZoneOffset.ofTotalSeconds(8);

        // creating and initializing
        // ZoneOffsetTransition Object
        ZoneOffsetTransition zonetrans1
            = ZoneOffsetTransition.of(
                loc, off1, off2);

        // getting the string representation
        // of this object
        // by using toString() method
        String str = zonetrans1.toString();

        // display the result
        System.out.println(
            "zone offset transition : "
            + str);
    }
}
```

**输出:**

> 区域偏移过渡:过渡【重叠于 1999-04-25T03:24:45+00:00:12 至+00:00:08】

**示例 2:**

```
// Java program to demonstrate
// toString() method

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
            = ZoneOffset.ofTotalSeconds(45);

        // creating and initializing
        // the object of ZoneOffset
        ZoneOffset off2
            = ZoneOffset.ofTotalSeconds(20);

        // creating and initializing
        // ZoneOffsetTransition Object
        ZoneOffsetTransition zonetrans1
            = ZoneOffsetTransition.of(
                loc, off1, off2);

        // getting the string representation
        // of this object
        // by using toString() method
        String str = zonetrans1.toString();

        // display the result
        System.out.println(
            "zone offset transition : "
            + str);
    }
}
```

**输出:**

> 区域偏移过渡:过渡【重叠于 1999-04-25T03:24:45+00:00:45 至+00:00:20】

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/zoneoffsettransition . html # toString–](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransition.html#toString--)