# ZoneOffsetTransition 是 Java 中的一个有效的 Offset()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransition-is valid offset-method-in-Java-with-example/](https://www.geeksforgeeks.org/zoneoffsettransition-isvalidoffset-method-in-java-with-example/)

**Java . time . zone . zoneoffset transition**类的 **isValidOffset()** 方法用于检查在转换过程中特定的区域偏移是否有效。

**语法:**

```java
public boolean isValidOffset(ZoneOffset offset)
```

**参数:**该方法用于将区域偏移对象的类型作为参数。

**返回值:**如果在转换期间特定区域偏移有效或无效，则该方法返回真，否则返回假。

以下是说明 **isValidOffset()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// isValidOffset() method

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
        // isValidOffset() method
        boolean status
            = zonetrans1
                  .isValidOffset(
                      ZoneOffset
                          .ofTotalSeconds(24));

        // display the result
        if (status)
            System.out.println("zoneoffset is valid");
        else
            System.out.println("zoneoffset is invalid");
    }
}
```

**输出:**

```java
zoneoffset is invalid

```

**例 2:**

```java
// Java program to demonstrate
// isValidOffset() method

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
            = ZoneOffset.ofTotalSeconds(12);

        // creating and initializing
        // ZoneOffsetTransition Object
        ZoneOffsetTransition zonetrans1
            = ZoneOffsetTransition.of(
                loc, off1, off2);

        // comparing both object using
        // isValidOffset() method
        boolean status
            = zonetrans1.isValidOffset(off1);

        // display the result
        if (status)
            System.out.println("zoneoffset is valid");
        else
            System.out.println("zoneoffset is invalid");
    }
}
```

**输出:**

```java
zoneoffset is valid

```

**输出:**

```java
zoneoffset is valid

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/zone/zoneoffsettransition . html # isvalid offset-Java . time . zoneoffset-](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransition.html#isValidOffset-java.time.ZoneOffset-)