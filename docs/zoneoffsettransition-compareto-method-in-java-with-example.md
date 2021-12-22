# Java 中的 ZoneOffsetTransition compareTo()方法与示例

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransition-compare to-method-in-Java-with-example/](https://www.geeksforgeeks.org/zoneoffsettransition-compareto-method-in-java-with-example/)

类的 **compareTo()** 方法用于在 ZoneOffsetTransition 类型的两个对象之间进行比较。比较是基于过渡时刻进行的。

**语法:**

```java
public int compareTo(ZoneOffsetTransition transition)
```

**参数:**该方法取一个 ZoneoffsetTransition 类型的过渡，并与该过渡进行比较。

**返回值:**如果 ZoneOffsetTransition 的两个对象相等，则此方法返回零，如果传递的转换小于此转换，则返回负值，如果传递的转换大于此转换，则返回正值。

以下是举例说明 **compareTo()** 方法的例子:

**例 1:**

```java
// Java program to demonstrate
// compareTo() method

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

        // Creating and initializing
        // ZoneOffsetTransition Object
        ZoneOffsetTransition zonetrans2
            = ZoneOffsetTransition.of(
                loc, off1, off2);

        // Comparing both object using
        // compareTo() method
        int status
            = zonetrans1.compareTo(
                zonetrans2);

        // Display the result
        if (status == 0)
            System.out.println(
                "zonetrans1 is equal to zonetrans2");
        else if (status > 0)
            System.out.println(
                "zonetrans1 is greater than zonetrans2");
        else
            System.out.println(
                "zonetrans1 is lesser than zonetrans2");
    }
}
```

**输出:**

```java
zonetrans1 is equal to zonetrans2

```

**例 2:**

```java
// Java program to demonstrate
// compareTo() method

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

        // Creating and initializing
        // ZoneOffsetTransition Object
        ZoneOffsetTransition zonetrans2
            = ZoneOffsetTransition.of(
                loc, off2, off1);

        // Comparing both object using
        // compareTo() method
        int status
            = zonetrans1.compareTo(
                zonetrans2);

        // Display the result
        if (status == 0)
            System.out.println(
                "zonetrans1 is equal to zonetrans2");
        else if (status > 0)
            System.out.println(
                "zonetrans1 is greater than zonetrans2");
        else
            System.out.println(
                "zonetrans1 is lesser than zonetrans2");
    }
}
```

**输出:**

```java
zonetrans1 is greater than zonetrans2

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/zoneoffsettransition . html # compare to-Java . time . zoneoffsettransition-](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransition.html#compareTo-java.time.zone.ZoneOffsetTransition-)