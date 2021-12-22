# Java 中的 SimpleDateFormat hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/simpledateform-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpledateformat-hashcode-method-in-java-with-examples/)

**SimpleDateFormat 类**的 **hashCode()** 方法用于返回这个 SimpleDateFormat 对象的哈希码值。哈希代码是整数类型。

**语法:**

```
public int hashCode()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回这个 SimpleDateFormat 对象的哈希码值，并且是整数类型。

下面的程序说明了简单日期格式的 hashCode()方法的工作原理:

**例 1:**

```
// Java to illustrate hashCode() method

import java.text.*;
import java.util.*;

public class SimpleDateFormat_Demo {
    public static void main(String[] args)
        throws InterruptedException
    {
        // Initializing SimpleDateFormat
        SimpleDateFormat SDFormat
            = new SimpleDateFormat(
                "dd/MM/yyyy");

        // Displaying the formats
        Date date = new Date();
        String str_Date1 = SDFormat.format(date);
        System.out.println("The Original: "
                           + (str_Date1));

        // Displaying the hash code
        System.out.println("The hash code: "
                           + SDFormat.hashCode());
    }
}
```

**Output:**

```
The Original: 30/01/2019
The hash code: -650712384

```

**例 2:**

```
// Java to illustrate hashCode() method

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
        String str_Date1 = SDFormat.format(date);
        System.out.println("The Original: "
                           + (str_Date1));

        // Displaying the hash code
        System.out.println("The hash code: "
                           + SDFormat.hashCode());
    }
}
```

**Output:**

```
The Original: 01/30/2019
The hash code: 2087096576

```