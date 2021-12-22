# Java 中的属性键集()方法，示例

> 原文:[https://www . geesforgeks . org/properties-key set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/properties-keyset-method-in-java-with-examples/)

**[属性类](https://www.geeksforgeeks.org/java-util-properties-class-java/)** 的**键集()**方法用于创建属性中包含的一组关键元素。它基本上返回一个键的集合视图，或者我们可以创建一个新的集合并将键元素存储在其中。

**语法:**

```java
public Set keySet()
```

**参数:**该方法不接受参数

**返回:**该方法返回包含在该属性对象中的键的**集合视图**。

下面的程序展示了 int keySet()方法的实现。

**程序 1:**

```java
// Java code to show the implementation of
// keySet() method

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

        System.out.println("keySet: "
                           + properties.keySet());
    }
}
```

**输出:**

```java
Properties: {Book=500, Mobile=5000, Pen=10, Clothes=400}
keySet: [Book, Mobile, Pen, Clothes]

```

**程序二:**

```java
// Java program to demonstrate
// keySet() method.

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

        System.out.println("keySet: "
                           + properties.keySet());
    }
}
```

**输出:**

```java
Current Properties: {You=30, Welcomes=25, 4=15, Geeks=20}
keySet: [You, Welcomes, 4, Geeks]

```

参考资料:[https://docs . Oracle . com/javase/9/docs/API/Java/util/properties . html # KeySet–](https://docs.oracle.com/javase/9/docs/api/java/util/Properties.html#keySet--)