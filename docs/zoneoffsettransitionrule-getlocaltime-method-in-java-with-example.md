# Java 中的 ZoneOffsetTransitionRule getLocalTime()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransitionrule-getlocaltime-in-Java-method-with-example/](https://www.geeksforgeeks.org/zoneoffsettransitionrule-getlocaltime-method-in-java-with-example/)

类的 **getLocalTime()** 方法用于获取发生转换的本地时间对象。

**语法:**

```java
public LocalTime getLocalTime()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回将要发生转换的本地时间对象。

下面是举例说明 **getLocalTime()** 方法的例子:

**例 1:**

```java
// Java program to demonstrate
// getLocalTime() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.zone.*;

public class GFG {
    public static void main(String[] argv)
    {

        // creating and initializing
        // ZoneOffsetTransitionRule Object
        ZoneOffsetTransitionRule zonetrans1
            = ZoneOffsetTransitionRule
                  .of(
                      Month.JANUARY, 12,
                      DayOfWeek.SUNDAY,
                      LocalTime.of(03, 24, 45),
                      false,
                      ZoneOffsetTransitionRule
                          .TimeDefinition
                          .STANDARD,
                      ZoneOffset.ofTotalSeconds(8),
                      ZoneOffset.ofTotalSeconds(10),
                      ZoneOffset.ofTotalSeconds(12));

        // getting object of local time
        // by using getLocalTime() method
        LocalTime loc
            = zonetrans1.getLocalTime();

        // display the result
        System.out.println(
            "Local Time : " + loc);
    }
}
```

**输出:**

```java
Local Time : 03:24:45

```

**例 2:**

```java
// Java program to demonstrate
// getLocalTime() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.zone.*;

public class GFG {
    public static void main(String[] argv)
    {

        // creating and initializing
        // ZoneOffsetTransitionRule Object
        ZoneOffsetTransitionRule zonetrans1
            = ZoneOffsetTransitionRule
                  .of(
                      Month.JANUARY, 12,
                      DayOfWeek.SUNDAY,
                      LocalTime.of(04, 40, 45),
                      false,
                      ZoneOffsetTransitionRule
                          .TimeDefinition
                          .STANDARD,
                      ZoneOffset.ofTotalSeconds(8),
                      ZoneOffset.ofTotalSeconds(10),
                      ZoneOffset.ofTotalSeconds(12));

        // getting object of local time
        // by using getLocalTime() method
        LocalTime loc = zonetrans1.getLocalTime();

        // display the result
        System.out.println("Local Time : " + loc);
    }
}
```

**输出:**

```java
Local Time : 04:40:45

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/zone/zoneoffsettransition rule . html # get local–](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransitionRule.html#getLocalTime--)