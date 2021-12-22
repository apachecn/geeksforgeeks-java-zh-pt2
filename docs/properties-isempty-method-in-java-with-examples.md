# 属性 Java 中的 isEmpty()方法，示例

> 原文:[https://www . geesforgeks . org/properties-isempty-method-in-Java-with-examples/](https://www.geeksforgeeks.org/properties-isempty-method-in-java-with-examples/)

**[属性类](https://www.geeksforgeeks.org/java-util-properties-class-java/)** 的 **isEmpty()** 方法用于检查该属性对象是否为空。

**语法:**

```
public boolean isEmpty()
```

**参数:**该方法不接受参数

**返回:**该方法返回一个**布尔值**，说明该属性对象是否为空。

下面的程序展示了 int isEmpty()方法的实现。

**程序 1:**

```
// Java code to show the implementation of
// isEmpty method

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

        // Checking if the Properties is empty
        System.out.println("Is Properties empty: "
                           + properties.isEmpty());
    }
}
```

**输出:**

```
Properties: {Book=500, Mobile=5000, Pen=10, Clothes=400}
Is Properties empty: false

```

**程序二:**

```
// Java program to demonstrate
// isEmpty() method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // Create a properties and add some values
        Properties properties = new Properties();

        // Print Properties details
        System.out.println("Current Properties: "
                           + properties.toString());

        // Checking if the Properties is empty
        System.out.println("Is Properties empty: "
                           + properties.isEmpty());
    }
}
```

**输出:**

```
Current Properties: {}
Is Properties empty: true

```

参考文献:[https://docs . Oracle . com/javase/9/docs/API/Java/util/properties . html # isEmpty–](https://docs.oracle.com/javase/9/docs/api/java/util/Properties.html#isEmpty--)