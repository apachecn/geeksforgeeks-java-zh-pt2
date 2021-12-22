# ZoneOffsetTransition getOffsetAfter()方法在 Java 中用示例

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransition-getoffsetafter-method-in-Java-with-example/](https://www.geeksforgeeks.org/zoneoffsettransition-getoffsetafter-method-in-java-with-example/)

使用**Java . time . zoneoffsettransition**类的 **getOffsetAfter()** 方法获取转换发生后第二个偏移区域的偏移值。第一个和第二个偏移量是指创建区域偏移转换对象时传递的值。

**语法:**

```java
public ZoneOffset getOffsetAfter()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回过渡发生后第二个区域偏移的偏移值。它不返回空值。

以下是举例说明 **getOffsetAfter()** 方法的例子:

**例 1:**

```java
// Java program to demonstrate
// getOffsetAfter() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.zone.*;

public class GFG {
    public static void main(String[] argv)
    {

        // Creating and initializing the
        // object of LocalDateTime
        LocalDateTime loc
            = LocalDateTime.of(
                1999, 04, 25, 03,
                24, 45, 0);

        // Creating and initializing the
        // object of ZoneOffset
        ZoneOffset off1
            = ZoneOffset.ofTotalSeconds(
                8);

        // Creating and initializing the
        // object of ZoneOffset
        ZoneOffset off2
            = ZoneOffset.ofTotalSeconds(
                12);

        // Creating and initializing
        // ZoneOffsetTransition Object
        ZoneOffsetTransition zonetrans1
            = ZoneOffsetTransition.of(
                loc, off1, off2);

        // Getting the offset after value
        // by using getOffsetAfter() method
        ZoneOffset off
            = zonetrans1.getOffsetAfter();

        // Display the result
        System.out.println(
            "Zoneoffset after transition : "
            + off);
    }
}
```

**输出:**

```java
Zoneoffset after transition : +00:00:12

```

**例 2:**

```java
// Java program to demonstrate
// getOffsetAfter() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.zone.*;

public class GFG {
    public static void main(String[] argv)
    {

        // Creating and initializing the
        // object of LocalDateTime
        LocalDateTime loc
            = LocalDateTime.of(
                1999, 04, 25, 03,
                24, 45, 0);

        // Creating and initializing the
        // object of ZoneOffset
        ZoneOffset off1
            = ZoneOffset.ofTotalSeconds(
                12);

        // Creating and initializing the
        // object of ZoneOffset
        ZoneOffset off2
            = ZoneOffset.ofTotalSeconds(
                8);

        // Creating and initializing
        // ZoneOffsetTransition Object
        ZoneOffsetTransition zonetrans1
            = ZoneOffsetTransition.of(
                loc, off1, off2);

        // Getting the offset after value
        // by using getOffsetAfter() method
        ZoneOffset off
            = zonetrans1.getOffsetAfter();

        // Display the result
        System.out.println(
            "Zoneoffset after transition : "
            + off);
    }
}
```

**输出:**

```java
Zoneoffset after transition : +00:00:08

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/zoneoffsettransition . html # getOffsetAfter–](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransition.html#getOffsetAfter--)