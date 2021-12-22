# Java 中的 ZoneOffsetTransition getOffsetBefore()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransition-getoffsetbefore-method-in-Java-with-example/](https://www.geeksforgeeks.org/zoneoffsettransition-getoffsetbefore-method-in-java-with-example/)

**Java . time . zoneoffsettransition**类的 **getOffsetBefore()** 方法用于获取作为参数传递的第一个区域偏移对象的偏移值。

**语法:**

```java
public ZoneOffset getOffsetBefore()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回作为参数传递的第一个区域偏移对象的偏移值。

下面是举例说明 **getOffsetBefore()** 方法的例子:

**例 1:**

```java
// Java program to demonstrate
// getOffsetBefore() method

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

        // getting the offset before value
        // by using getOffsetBefore() method
        ZoneOffset off
            = zonetrans1.getOffsetBefore();

        // display the result
        System.out.println(
            "Zoneoffset before transition : "
            + off);
    }
}
```

**输出:**

```java
Zoneoffset before transition : +00:00:08

```

**例 2:**

```java
// Java program to demonstrate
// getOffsetBefore() method

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

        // getting the offset before value
        // by using getOffsetBefore() method
        ZoneOffset off
            = zonetrans1.getOffsetBefore();

        // display the result
        System.out.println(
            "Zoneoffset before transition : "
            + off);
    }
}
```

**输出:**

```java
Zoneoffset before transition : +00:00:12

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/zone/zoneoffsettransition . html # getffset before】](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransition.html#getOffsetBefore--)