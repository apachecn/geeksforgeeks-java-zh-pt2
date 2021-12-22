# Java 中的属性键()方法，示例

> 原文:[https://www . geesforgeks . org/properties-keys-method-in-Java-with-examples/](https://www.geeksforgeeks.org/properties-keys-method-in-java-with-examples/)

**[属性类](https://www.geeksforgeeks.org/java-util-properties-class-java/)** 的**键()**方法用于获取该属性对象中键的枚举。此枚举可用于顺序遍历和迭代键。

**语法:**

```
public Enumeration keys()
```

**参数:**该方法不接受参数

**返回:**该方法依次返回该属性对象的键的 **[枚举](https://www.geeksforgeeks.org/iterators-in-java/)** 。

下面的程序展示了 int keys()方法的实现。

**程序 1:**

```
// Java code to show the implementation of
// keys() method

import java.util.*;
public class GfG {

    // Main method
    public static void main(String[] args)
    {

        // Create a properties and add some values
        Properties properties = new Properties();
        properties.put("Pen", 10);
        properties.put("Book", 500);
        properties.put("Clothes", 400);
        properties.put("Mobile", 5000);

        // Print Properties details
        System.out.println("Properties: "
                           + properties.toString());

        // Creating an empty enumeration to store
        Enumeration enu = properties.keys();

        System.out.println("The enumeration of keys are:");

        // Displaying the Enumeration
        while (enu.hasMoreElements()) {
            System.out.println(enu.nextElement());
        }
    }
}
```

**输出:**

```
Properties: {Book=500, Mobile=5000, Pen=10, Clothes=400}
The enumeration of keys are:
Book
Mobile
Pen
Clothes

```

**程序二:**

```
// Java program to demonstrate
// keys() method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // Create a properties and add some values
        Properties properties = new Properties();

        // Inserting elements into the properties
        properties.put("Geeks", 10);
        properties.put("4", 15);
        properties.put("Geeks", 20);
        properties.put("Welcomes", 25);
        properties.put("You", 30);

        // Print Properties details
        System.out.println("Current Properties: "
                           + properties.toString());

        // Creating an empty enumeration to store
        Enumeration enu = properties.keys();

        System.out.println("The enumeration of keys are:");

        // Displaying the Enumeration
        while (enu.hasMoreElements()) {
            System.out.println(enu.nextElement());
        }
    }
}
```

**输出:**

```
Current Properties: {You=30, Welcomes=25, 4=15, Geeks=20}
The enumeration of keys are:
You
Welcomes
4
Geeks

```

参考文献:[https://docs . Oracle . com/javase/9/docs/API/Java/util/properties . html # keys–](https://docs.oracle.com/javase/9/docs/api/java/util/Properties.html#keys--)