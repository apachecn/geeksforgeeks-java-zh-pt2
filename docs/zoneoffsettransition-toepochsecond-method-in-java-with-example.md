# Java 中的 ZoneOffsetTransition to pochssecond()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransition-toepochssecond-method-in-Java-with-example/](https://www.geeksforgeeks.org/zoneoffsettransition-toepochsecond-method-in-java-with-example/)

**Java . time . zone . zoneoffset transition**类的**to pochssecond()**方法用于获取该特定区域偏移转换对象的第二个纪元。

**语法:**

```java
public long toEpochSecond()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回该特定区域偏移过渡对象的历元秒。

以下是说明**至**方法的示例:

**例 1:**

```java
// Java program to demonstrate
// toEpochSecond() method

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

        // getting the epoch second for this object
        // by using toEpochSecond() method
        long epocsec
            = zonetrans1.toEpochSecond();

        // display the result
        System.out.println(
            "epoch second : "
            + epocsec);
    }
}
```

**输出:**

```java
epoch second : 925010677

```

**例 2:**

```java
// Java program to demonstrate
// toEpochSecond() method

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

        // getting the epoch second for this object
        // by using toEpochSecond() method
        long epocsec
            = zonetrans1.toEpochSecond();

        // display the result
        System.out.println("epoch second : "
                           + epocsec);
    }
}
```

**输出:**

```java
epoch second : 925010673

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/zoneoffsettransition . html # to pochssecond–](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransition.html#toEpochSecond--)