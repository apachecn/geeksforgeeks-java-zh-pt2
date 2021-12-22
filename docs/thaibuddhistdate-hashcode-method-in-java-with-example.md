# Java 中的 ThaiBuddhistDate hashCode()方法，示例

> 原文:[https://www . geeksforgeeks . org/thaibudhistate-hashcode-method-in-Java-with-example/](https://www.geeksforgeeks.org/thaibuddhistdate-hashcode-method-in-java-with-example/)

类的 **hashCode()** 方法用于获取特定 ThaiBuddhist 日期的哈希代码。

**语法:**

```
public int hashCode()
```

**参数:**此方法不接受任何参数作为参数。

**返回值:**该方法返回特定泰国历史日期的[哈希代码](https://www.geeksforgeeks.org/equals-hashcode-methods-java/)。

下面是举例说明 **hashCode()** 方法的例子:

**例 1:**

```
// Java program to demonstrate
// hashCode() method

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

            // Getting hash code of the date
            // by using hashCode() method
            long tempo
                = hidate.hashCode();

            // Display the result
            System.out.println(
                "Hashcode: "
                + tempo);
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

```
Hashcode: 143308498

```

**例 2:**

```
// Java program to demonstrate
// hashCode() method

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
                = ThaiBuddhistDate.of(1345, 06, 13);

            // Getting hash code of the date
            // by using hashCode() method
            long tempo
                = hidate.hashCode();

            // Display the result
            System.out.println(
                "Hashcode: "
                + tempo);
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

```
Hashcode: 145524252

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/thaibuddhistdate . html # hashCode–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ThaiBuddhistDate.html#hashCode--)