# Java 中的 ZoneOffsetTransitionRule equals()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransitionrule-equals-method-in-Java-with-example/](https://www.geeksforgeeks.org/zoneoffsettransitionrule-equals-method-in-java-with-example/)

类的 **equals()** 方法用于比较区域偏移转换规则类型的两个对象。

**语法:**

```java
public boolean equals(Object other)
```

**参数:**该方法以其他 ZoneOffsetTransitionRule 的对象为参数。

**返回值:**如果两个对象相等，该方法返回真，否则返回假。

以下是说明**等于()**方法的示例:

**例 1:**

```java
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

        // creating and initializing
        // ZoneOffsetTransitionRule Object
        ZoneOffsetTransitionRule zonetrans2
            = ZoneOffsetTransitionRule.of(
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

```java
zonetrans1 is equal to zonetrans2

```

**例 2:**

```java
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

        // creating and initializing
        // ZoneOffsetTransitionRule Object
        ZoneOffsetTransitionRule zonetrans2
            = ZoneOffsetTransitionRule
                  .of(
                      Month.JANUARY, 16,
                      DayOfWeek.SUNDAY,
                      LocalTime.of(03, 24, 45),
                      false,
                      ZoneOffsetTransitionRule
                          .TimeDefinition
                          .STANDARD,
                      ZoneOffset
                          .ofTotalSeconds(8),
                      ZoneOffset
                          .ofTotalSeconds(10),
                      ZoneOffset
                          .ofTotalSeconds(12));

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

```java
zonetrans1 is not equal to zonetrans2

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/zoneoffsettransitionrule . html # equals-Java . lang . object-](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransitionRule.html#equals-java.lang.Object-)