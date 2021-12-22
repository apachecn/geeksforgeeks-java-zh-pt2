# Java 中的 ThaiBuddhistDate lengthOfMonth()方法，示例

> 原文:[https://www . geeksforgeeks . org/thaibudhistdata-length of month-in-method-in-Java-with-example/](https://www.geeksforgeeks.org/thaibuddhistdate-lengthofmonth-method-in-java-with-example/)

**Java . time . chrono . thaibudhistate**类的 **lengthOfMonth()** 方法用于获取由特定 thaibudhistate 日期表示的一个月中存在的天数。

**语法:**

```java
public int lengthOfMonth()
```

**参数:**此方法不接受任何参数作为参数。

**返回值:**该方法返回一个月中由特定的 ThaiBuddhist 日期表示的天数。

以下是说明**月长()**方法的示例:

**例 1:**

```java
// Java program to demonstrate
// lengthOfMonth() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate
                = ThaiBuddhistDate.now();

            // Getting length of a month
            // by using lengthOfMonth() method
            int length
                = hidate.lengthOfMonth();

            // Display the result
            System.out.println(
                "Number of day present: "
                + length);
        }
        catch (DateTimeException e) {
            System.out.println(
                "Passed parameter can"
                + " not form a date");

            System.out.println(
                "Exception thrown: "
                + e);
        }
    }
}
```

**输出:**

```java
Number of day present: 31

```

**例 2:**

```java
// Java program to demonstrate
// lengthOfMonth() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate
                = ThaiBuddhistDate.of(2020, 06, 23);

            // Getting length of a month
            // by using lengthOfMonth() method
            int length
                = hidate.lengthOfMonth();

            // Display the result
            System.out.println(
                "Number of day present: "
                + length);
        }
        catch (DateTimeException e) {

            System.out.println(
                "Passed parameter can"
                + " not form a date");

            System.out.println(
                "Exception thrown: "
                + e);
        }
    }
}
```

**输出:**

```java
Number of day present: 30

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibuddhistdate . html # length of month–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistDate.html#lengthOfMonth--)