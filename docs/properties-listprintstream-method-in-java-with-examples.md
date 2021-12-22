# Java 中的属性列表(打印流)方法，示例

> 原文:[https://www . geesforgeks . org/properties-listprintstream-method-in-Java-with-examples/](https://www.geeksforgeeks.org/properties-listprintstream-method-in-java-with-examples/)

**[属性类](https://www.geeksforgeeks.org/java-util-properties-class-java/)** 的**列表(打印流)**方法用于将该属性列表打印到指定的输出流，作为参数传递。此方法可用于调试目的，因为它有助于查看流中的属性元素。0

**语法:**

```
public void list(PrintStream out)
```

**参数:**该方法接受一个参数**打印输出**，这是一个输出流，属性元素将被打印在该输出流上。

**返回:**这个方法只是打印元素，不返回任何东西。

下面的程序展示了 int list(PrintStream)方法的实现。

**程序 1:**

```
// Java code to show the implementation of
// list(PrintStream) method

import java.util.*;
public class GfG {

    // Main method
    public static void main(String[] args)
    {

        // Create a properties and add some values
        Properties properties = new Properties();
        properties.put("Pen", "10");
        properties.put("Book", "500");
        properties.put("Clothes", "400");
        properties.put("Mobile", "5000");

        // Print Properties details
        System.out.println("Properties: "
                           + properties.toString());

        System.out.println("listing out the Properties: ");
        properties.list(System.out);
    }
}
```

**输出:**

```
Properties: {Book=500, Mobile=5000, Pen=10, Clothes=400}
listing out the Properties: 
-- listing properties --
Book=500
Pen=10
Mobile=5000
Clothes=400

```

**程序二:**

```
// Java program to demonstrate
// list(PrintStream) method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // Create a properties and add some values
        Properties properties = new Properties();

        // Inserting elements into the properties
        properties.put("Geeks", "10");
        properties.put("4", "15");
        properties.put("Geeks", "20");
        properties.put("Welcomes", "25");
        properties.put("You", "30");

        // Print Properties details
        System.out.println("Properties: "
                           + properties.toString());

        System.out.println("listing out the Properties: ");
        properties.list(System.out);
    }
}
```

**输出:**

```
Properties: {You=30, Welcomes=25, 4=15, Geeks=20}
listing out the Properties: 
-- listing properties --
You=30
4=15
Welcomes=25
Geeks=20

```

参考文献:[https://docs . Oracle . com/javase/9/docs/API/Java/util/properties . html # list-Java . io . print stream-](https://docs.oracle.com/javase/9/docs/api/java/util/Properties.html#list-java.io.PrintStream-)