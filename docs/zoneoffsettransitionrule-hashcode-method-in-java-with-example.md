# Java 中的 ZoneOffsetTransitionRule hashCode()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransitionrule-hashcode-method-in-Java-with-example/](https://www.geeksforgeeks.org/zoneoffsettransitionrule-hashcode-method-in-java-with-example/)

使用**Java . time . zone . zoneoffsettransitionrule**类的 **hashCode()** 方法获取该区域偏移转换规则对象的哈希代码。

**语法:**

```java
public int hashCode()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回该区域偏移过渡规则对象的哈希码。

下面是举例说明 **hashCode()** 方法的例子:

**例 1:**

```java
// Java program to demonstrate
// hashCode() method

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
                      ZoneOffset.ofTotalSeconds(17),
                      ZoneOffset.ofTotalSeconds(12));

        // getting the hash code
        // by using hashCode() method
        int hash = zonetrans1.hashCode();

        // display the result
        System.out.println("hash code : " + hash);
    }
}
```

**输出:**

```java
hash code : 402556303

```

**例 2:**

```java
// Java program to demonstrate
// hashCode() method

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
                      LocalTime.of(06, 24, 45),
                      false,
                      ZoneOffsetTransitionRule
                          .TimeDefinition
                          .STANDARD,
                      ZoneOffset.ofTotalSeconds(8),
                      ZoneOffset.ofTotalSeconds(17),
                      ZoneOffset.ofTotalSeconds(12));

        // getting the hash code
        // by using hashCode() method
        int hash = zonetrans1.hashCode();

        // display the result
        System.out.println("hash code : " + hash);
    }
}
```

**输出:**

```java
hash code : 756450703

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/zone/zoneoffsettransition rule . html # hashcode--](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransitionRule.html#hashCode--)