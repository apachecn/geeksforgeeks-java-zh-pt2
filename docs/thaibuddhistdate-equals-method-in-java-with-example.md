# Java 中的 ThaiBuddhistDate 等于()方法，示例

> 原文:[https://www . geeksforgeeks . org/thaibudhistate-equals-method-in-Java-with-example/](https://www.geeksforgeeks.org/thaibuddhistdate-equals-method-in-java-with-example/)

**Java . time . chrono . thaibudhistate**类的 **equals()** 方法用于比较两个 thaibudhistate 日期，并检查两者是否相同。

**语法:**

```java
public boolean equals(Object obj)
```

**参数:**该方法以一个等价的**对象**作为参数与[这个](https://www.geeksforgeeks.org/this-reference-in-java/)thaibudhistate 进行比较。

**返回值:**如果两个日期相等，该方法返回真，否则返回假。

以下是说明**等于()**方法的示例:

**例 1:**

```java
// Java program to demonstrate
// equals() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate1
                = ThaiBuddhistDate.now();

            // Creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate2
                = ThaiBuddhistDate.now();

            // Comparing both date
            // by using equals() method
            boolean status
                = hidate1.equals(hidate2);

            // Display the result
            if (status)
                System.out.println(
                    "Both dates are equal");
            else
                System.out.println(
                    "Both dates are not equal");
        }
        catch (DateTimeException e) {
            System.out.println(
                "Passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
Both dates are equal

```

**例 2:**

```java
// Java program to demonstrate
// equals() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate1
                = ThaiBuddhistDate.now();

            // Creating and initializing
            // ThaiBuddhistDate Object
            ThaiBuddhistDate hidate2
                = ThaiBuddhistDate.of(2008, 03, 23);

            // Comparing both date
            // by using equals() method
            boolean status
                = hidate1.equals(hidate2);

            // Display the result
            if (status)
                System.out.println(
                    "Both dates are equal");
            else
                System.out.println(
                    "Both dates are not equal");
        }
        catch (DateTimeException e) {
            System.out.println(
                "Passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
Both dates are not equal

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibudhistate . html # equals-Java . lang . object-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistDate.html#equals-java.lang.Object-)