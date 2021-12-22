# Java 中属性 hashCode()方法示例

> 原文:[https://www . geesforgeks . org/properties-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/properties-hashcode-method-in-java-with-examples/)

**[属性类](https://www.geeksforgeeks.org/java-util-properties-class-java/)** 的 **hashCode()** 方法用于为包含键和值的给定属性生成 hashCode。

**语法:**

```java
public int hashCode()
```

**参数:**这个方法没有参数。

**返回:**该方法返回给定地图的 hashCode 值。

下面的程序展示了 int hashCode()方法的实现。

**程序 1:**

```java
// Java code to show the implementation of
// hashCode method

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

        // Getting the hashCode value
        System.out.println("HashCode: "
                           + properties.hashCode());
    }
}
```

**输出:**

```java
Properties: {Book=500, Mobile=5000, Pen=10, Clothes=400}
HashCode: 548388082

```

**程序二:**

```java
// Java program to demonstrate
// hashCode() method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // Create a properties and add some values
        Properties properties = new Properties();

        properties.put(1, "100RS");
        properties.put(2, "500RS");
        properties.put(3, "1000RS");

        // Print Properties details
        System.out.println("Current Properties: "
                           + properties.toString());

        // Getting the hashCode value
        System.out.println("HashCode: "
                           + properties.hashCode());
    }
}
```

**输出:**

```java
Current Properties: {3=1000RS, 2=500RS, 1=100RS}
HashCode: 1545792714

```

参考文献:[https://docs . Oracle . com/javase/9/docs/API/Java/util/properties . html # hashCode–](https://docs.oracle.com/javase/9/docs/api/java/util/Properties.html#hashCode--)