# Java 中的属性等于(值)方法，示例

> 原文:[https://www . geesforgeks . org/properties-equals value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/properties-equalsvalue-method-in-java-with-examples/)

**[属性类](https://www.geeksforgeeks.org/java-util-properties-class-java/)** 的**等于(值)**方法用于检查两个属性之间的相等性。它验证作为参数传递的一个属性对象的元素是否等于该属性的元素。

**语法:**

```java
public boolean equals(Object value)
```

**参数:**该方法接受该属性类型的参数**值**，并引用要用该映射检查其相等性的映射。

**返回:**该方法返回一个**布尔**值，说明两个对象属性是否相等。

下面的程序说明了 equals(值)方法:

**程序 1:**

```java
// Java program to demonstrate
// equals(value) method.

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
        System.out.println("Properties 1: "
                           + properties.toString());

        // Create another properties and add some values
        Properties properties1 = new Properties();
        properties1.put("Pen", 10);
        properties1.put("Book", 500);
        properties1.put("Clothes", 400);
        properties1.put("Mobile", 5000);

        // Print Properties details
        System.out.println("Properties 2: "
                           + properties1.toString());

        // Checking the equality
        System.out.println("Are both properties equal: "
                           + properties.equals(properties1));
    }
}
```

**输出:**

```java
Properties 1: {Book=500, Mobile=5000, Pen=10, Clothes=400}
Properties 2: {Book=500, Mobile=5000, Pen=10, Clothes=400}
Are both properties equal: true

```

**程序二:**

```java
// Java program to demonstrate
// equals(value) method.

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

        // Create another properties and add some values
        Properties properties1 = new Properties();
        properties1.put("Pen", 10);
        properties1.put("Book", 500);
        properties1.put("Clothes", 400);
        properties1.put("Mobile", 5000);

        // Print Properties details
        System.out.println("Properties 2: "
                           + properties1.toString());

        // Checking the equality
        System.out.println("Are both properties equal: "
                           + properties.equals(properties1));
    }
}
```

**输出:**

```java
Current Properties: {3=1000RS, 2=500RS, 1=100RS}
Properties 2: {Book=500, Mobile=5000, Pen=10, Clothes=400}
Are both properties equal: false

```

参考文献:[https://docs . Oracle . com/javase/9/docs/API/Java/util/properties . html # equals-Java . lang . object-](https://docs.oracle.com/javase/9/docs/api/java/util/Properties.html#equals-java.lang.Object-)