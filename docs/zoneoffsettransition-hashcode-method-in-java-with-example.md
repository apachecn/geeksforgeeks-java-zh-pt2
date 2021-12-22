# Java 中的 ZoneOffsetTransition hashCode()方法，示例

> 原文:[https://www . geeksforgeeks . org/zoneoffsettransition-hashcode-method-in-Java-with-example/](https://www.geeksforgeeks.org/zoneoffsettransition-hashcode-method-in-java-with-example/)

**Java . time . zone . zoneoffsettransition**类的 **hashCode()** 方法用于获取区域偏移转换对象的哈希代码。

**语法:**

```
public int hashCode()
```

**参数:**此方法不接受任何参数。

**返回值:**此方法返回区域偏移转换对象的哈希代码。

下面是举例说明 **hashCode()** 方法的例子:

**例 1:**

```
// Java program to demonstrate
// hashcode() method

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

        // getting the hash code for this object
        // by using hashcode() method
        int hash = zonetrans1.hashCode();

        // display the result
        System.out.println("hashcode : " + hash);
    }
}
```

**输出:**

```
hashcode : 1396559933

```

**例 2:**

```
// Java program to demonstrate
// hashcode() method

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
                2010, 04, 25,
                03, 56, 45, 0);

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

        // getting the hash code for this object
        // by using hashcode() method
        int hash = zonetrans1.hashCode();

        // display the result
        System.out.println("hashcode : " + hash);
    }
}
```

**输出:**

```
hashcode : 1539866618

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/zoneoffsettransition . html # hashCode–](https://docs.oracle.com/javase/9/docs/api/java/time/zone/ZoneOffsetTransition.html#hashCode--)