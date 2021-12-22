# Java 中的 SimpleDateFormat 等于()方法，示例

> 原文:[https://www . geesforgeks . org/simpledateform-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpledateformat-equals-method-in-java-with-examples/)

**简单日期格式类**的**等于()**方法用于比较两个简单日期格式对象。如果此简单日期格式等于传递的对象，则方法返回真，否则返回假。

**语法:**

```
public boolean equals(Object *obj*)
```

**参数:**该方法采用*对象*类型的一个参数**对象**，并引用要与该简单日期格式对象进行比较的对象。

**返回值:**如果两个对象相等，则该方法返回布尔真，否则该方法返回假。

以下程序说明了简单日期格式的 equals()方法的工作:
**示例 1:**

```
// Java code to illustrate equals() method

import java.text.*;
import java.util.*;

public class SimpleDateFormat_Demo {
    public static void main(String[] args)
        throws InterruptedException, ParseException
    {
        // Initializing the first formatter
        SimpleDateFormat SDFormat1
            = new SimpleDateFormat();

        // Initializing the second formatter
        SimpleDateFormat SDFormat2
            = new SimpleDateFormat();

        // Displaying both the Formats
        Date date = new Date();
        String str_Date1
            = SDFormat1.format(date);
        System.out.println("First: "
                           + (str_Date1));

        String str_Date2
            = SDFormat2.format(date);
        System.out.println("Second: "
                           + (str_Date2));

        // Comparing both the objects
        System.out.println("Equality: "
                           + SDFormat1.equals(SDFormat2));
    }
}
```

**Output:**

```
First: 1/30/19 9:59 AM
Second: 1/30/19 9:59 AM
Equality: true

```

**例 2:**

```
// Java code to illustrate equals() method

import java.text.*;
import java.util.*;

public class SimpleDateFormat_Demo {
    public static void main(String[] args)
        throws InterruptedException, ParseException
    {
        // Initializing the first formatter
        SimpleDateFormat SDFormat1
            = new SimpleDateFormat();

        // Defining the SDFormat
        SDFormat1.applyPattern("MMM");

        // Initializing the second formatter
        SimpleDateFormat SDFormat2
            = new SimpleDateFormat();

        // Displaying both the Formats
        Date date = new Date();
        String str_Date1
            = SDFormat1.format(date);
        System.out.println("First: 
                           + (str_Date1));

        String str_Date2
            = SDFormat2.format(date);
        System.out.println("Second: "
                           + (str_Date2));

        // Comparing both the objects
        System.out.println("Equality: "
                           + SDFormat1.equals(SDFormat2));
    }
}
```

**Output:**

```
First: Jan
Second: 1/30/19 10:00 AM
Equality: false

```