# Java 中的 thaibudhistechronic getCalendarType()方法，示例

> 原文:[https://www . geeksforgeeks . org/thaibudhistderor-getcalendartype-method-in-Java-with-example/](https://www.geeksforgeeks.org/thaibuddhistchronology-getcalendartype-method-in-java-with-example/)

**Java . time . chrono . ThaiBuddhist**类的 **getCalendarType()** 方法用于检索该 thaibudhistory 系统下的日历类型。
**语法:**

```java
public String getCalendarType()
```

**参数:**此方法不接受任何参数作为参数。
**返回值:**此方法返回的**类型的日历**位于此 ThaiBuddhist 时间系统下。
以下是举例说明 **getCalendarType()** 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getCalendarType() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing
        // ThaiBuddhistDate Object
        ThaiBuddhistDate hidate
            = ThaiBuddhistDate.now();

        // getting ThaiBuddhistChronology
        // used in ThaiBuddhistDate
        ThaiBuddhistChronology crono
            = hidate.getChronology();

        // getting type of Calendar
        // by using getCalendarType() method
        String era = crono.getCalendarType();

        // display the result
        System.out.println("Type of Calendar : "
                           + era);
    }
}
```

**Output**

```java
Type of Calendar : buddhist

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getCalendarType() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing
        // ThaiBuddhistDate Object
        ThaiBuddhistDate hidate
            = ThaiBuddhistDate.now(
                Clock.systemDefaultZone());

        // getting ThaiBuddhistChronology
        // used in ThaiBuddhistDate
        ThaiBuddhistChronology crono
            = hidate.getChronology();

        // getting type of Calendar
        // by using getCalendarType() method
        String era = crono.getCalendarType();

        // display the result
        System.out.println("Type of Calendar : "
                           + era);
    }
}
```

**Output**

```java
Type of Calendar : buddhist

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibudhistechrome . html # getCalendarType–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistChronology.html#getCalendarType--)