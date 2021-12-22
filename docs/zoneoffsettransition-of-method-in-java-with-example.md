# Java 中的 ZoneOffsetTransition()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransition-of-in-Java-in-method-with-example/](https://www.geeksforgeeks.org/zoneoffsettransition-of-method-in-java-with-example/)

**Java . time . zone . zoneoffsettransition**类的()方法的**用于借助本地日期时间、前后偏移来创建区域偏移过渡的对象。** 

**语法:**

```
public static ZoneOffsetTransition of(LocalDateTime transition,
                                      ZoneOffset offsetBefore,
                                      ZoneOffset offsetAfter)
```

**参数:**该方法将以下参数作为参数。

*   **转换:**必须为其创建转换的本地日期时间对象。
*   **偏移前:**初始过渡的区域偏移对象。
*   **偏移后:**最终过渡的区域偏移对象。

**返回值:**该方法借助本地日期时间、偏移前、偏移后返回区域偏移过渡的对象。
以下举例说明()法的**:
**例 1:****

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// of() method

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
        // by using of() method
        ZoneOffsetTransition zonetrans1
            = ZoneOffsetTransition.of(
                loc, off1, off2);

        // getting the string representation
        // of this object
        String str
            = zonetrans1.toString();

        // display the result
        System.out.println(
            "zone offset transition : "
            + str);
    }
}
```

**Output:** zone offset transition : Transition[Overlap at 1999-04-25T03:24:45+00:00:12 to +00:00:08]  

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// of() method

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
                2018, 04, 25,
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
        // by using of() method
        ZoneOffsetTransition zonetrans1
            = ZoneOffsetTransition.of(
                loc, off1, off2);

        // getting the string representation
        // of this object
        String str = zonetrans1.toString();

        // display the result
        System.out.println(
            "zone offset transition : "
            + str);
    }
}
```

**Output:** zone offset transition : Transition[Overlap at 2018-04-25T03:24:45+00:00:12 to +00:00:08]  

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/zoneoffset transition . html # of-Java . time . local datetime-Java . time . zoneoffset-Java . time . zoneoffset-](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransition.html#of-java.time.LocalDateTime-java.time.ZoneOffset-java.time.ZoneOffset-)