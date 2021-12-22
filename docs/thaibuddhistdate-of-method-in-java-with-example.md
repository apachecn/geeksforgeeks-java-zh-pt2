# Java 中()方法的 ThaiBuddhistDate，示例

> 原文:[https://www . geeksforgeeks . org/thaibudhistate-of-in-Java-in-method-with-example/](https://www.geeksforgeeks.org/thaibuddhistdate-of-method-in-java-with-example/)

**Java . time . chrono . ThaiBuddhistate**类的()方法的**用于根据 thaibudhist 日历系统，通过使用传递的前序年、月、日来生成日期。**

**语法:**

```java
public static ThaiBuddhistDate of(int Year,
            int month, int dayOfMonth)

```

**参数**:该方法以以下参数为参数:

*   **年份:**代表泰国历史日期中年份字段的整数值。
*   **月:**月的整数值，表示 ThaiBuddhist 日期中的月字段。
*   **日:**表示泰国历史日期中的日字段的整数值。

**返回值:**该方法根据泰国历系统，使用已通过的前序年、月、日返回**日期**。

**异常:**如果传递的参数不能形成日期，该方法抛出**日期时间异常**。

以下是举例说明()方法的**:**

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate of() method

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
            // By using of() method
            ThaiBuddhistDate hidate
                = ThaiBuddhistDate.of(1444, 04, 24);

            // Display the result
            System.out.println(
                "ThaiBuddhistDate: "
                + hidate);
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

**Output:**

> 泰国历史日期:泰国历史 BE 1444-04-24

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate of() method

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
            // By using of() method
            ThaiBuddhistDate hidate
                = ThaiBuddhistDate.of(1911, 04, -24);

            // Display the result
            System.out.println(
                "ThaiBuddhistDate: "
                + hidate);
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

**Output:**

> 传递的参数不能形成日期
> 抛出异常:Java . time . datetime 异常:DayOfMonth 的值无效(有效值 1–28/31):-24

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibuddhistdate . html # of-int-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistDate.html#of-int-int-int-)