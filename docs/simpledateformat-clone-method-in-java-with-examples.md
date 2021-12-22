# Java 中的 SimpleDateFormat clone()方法，示例

> 原文:[https://www . geesforgeks . org/simpledateform-clone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpledateformat-clone-method-in-java-with-examples/)

**简单日期格式类**的**克隆()**方法用于创建简单日期格式的副本。它创建了这个简单日期格式的另一个副本。

**语法:**

```
public Object clone()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回简单日期格式的副本。

下面的程序说明了简单日期格式的克隆()方法的工作原理:

**例 1:**

```
// Java to illustrate clone() method

import java.text.*;
import java.util.*;

public class SimpleDateFormat_Demo {
    public static void main(String[] args)
        throws InterruptedException
    {
        // Initializing SimpleDateFormat
        SimpleDateFormat SDFormat
            = new SimpleDateFormat(
                "MM/dd/yyyy");

        // Displaying the formats
        Date date = new Date();
        String str_Date1
            = SDFormat.format(date);
        System.out.println("The Original: "
                           + (str_Date1));

        // Using clone()
        System.out.println("Is the clone equal? "
                           + SDFormat
                                 .clone()
                                 .equals(SDFormat));
    }
}
```

**输出:**

```
The Original: 01/30/2019
Is the clone equal? true

```