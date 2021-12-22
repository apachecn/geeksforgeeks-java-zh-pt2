# Java 中的属性元素()方法，示例

> 原文:[https://www . geesforgeks . org/properties-elements-method-in-Java-with-examples/](https://www.geeksforgeeks.org/properties-elements-method-in-java-with-examples/)

[**属性类**](https://www.geeksforgeeks.org/java-util-properties-class-java/) 的**元素()**方法用于获取该属性对象的枚举。它还可以用于使用接收到的枚举按顺序检索元素。

**语法:**

```
public Enumeration elements()
```

**参数:**该方法不接受任何参数。
**返回:**该方法返回该属性对象中值的**枚举**。
以下程序说明了元素()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// elements() method.

import java.util.*;

public class GFG {

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
        System.out.println("Current Properties: "
                           + properties.toString());

        // Creating an empty enumeration to store
        Enumeration enu = properties.elements();

        System.out.println("The enumeration of values are:");

        // Displaying the Enumeration
        while (enu.hasMoreElements()) {
            System.out.println(enu.nextElement());
        }
    }
}
```

**Output:** 

```
Current Properties: {Book=500, Mobile=5000, Pen=10, Clothes=400}
The enumeration of values are:
500
5000
10
400
```