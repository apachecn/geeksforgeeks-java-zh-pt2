# Java 中的 ZoneOffsetTransition getInstant()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransition-getinstant-method-in-Java-with-example/](https://www.geeksforgeeks.org/zoneoffsettransition-getinstant-method-in-java-with-example/)

**Java . time . zone . zoneoffsettransition**类的 **getInstant()** 方法用于获取表示两个区域偏移之间转换的即时类型的对象。

**语法:**

```
public Instant getInstant()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回表示两个区域偏移之间过渡的即时类型的对象。

以下是说明 **getInstant()** 方法的示例:

**例 1:**

```
// Java program to demonstrate
// getInstant() method

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

        // getting the instant between two transition
        // by using getInstant() method
        Instant inst = zonetrans1.getInstant();

        // display the result
        System.out.println("Instant : " + inst);
    }
}
```

**输出:**

```
Instant : 1999-04-25T03:24:37Z

```

**例 2:**

```
// Java program to demonstrate
// getInstant() method

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

        // getting the instant between two transition
        // by using getInstant() method
        Instant inst = zonetrans1.getInstant();

        // display the result
        System.out.println("Instant : " + inst);
    }
}
```

**输出:**

```
Instant : 1999-04-25T03:24:33Z

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/zone/zoneoffsettransition . html # geti constant】](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransition.html#getInstant--)