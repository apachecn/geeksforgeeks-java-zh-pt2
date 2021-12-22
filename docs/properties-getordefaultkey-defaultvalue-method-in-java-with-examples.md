# Java 中属性 getOrDefault(key，defaultValue)方法，示例

> 原文:[https://www . geeksforgeeks . org/properties-getordefaultkey-defaultvalue-method-in-Java-with-examples/](https://www.geeksforgeeks.org/properties-getordefaultkey-defaultvalue-method-in-java-with-examples/)

**[属性类](https://www.geeksforgeeks.org/java-util-properties-class-java/)** 的 **getOrDefault(键，默认值)**方法用于获取映射到该键的值，在该属性对象中作为参数传递。此方法将获取该键的相应值(如果存在)，并返回它。如果没有这样的映射，那么它返回缺省值。

**语法:**

> 公共对象 getOrDefault(对象键，对象默认值)

**参数:**该方法接受两个参数:

*   **键**:要在该属性对象中检查其映射。
*   **默认值**:这是键的默认映射

**返回:**该方法返回与该键对应的**值**(如果存在)。如果没有这样的映射，那么它返回缺省值。

下面的程序说明了 getOrDefault(键，默认值)方法:

**程序 1:**

```java
// Java program to demonstrate
// getOrDefault(key, defaultValue) method.

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
        System.out.println("Properties: "
                           + properties.toString());

        // Getting the value of Pen
        System.out.println("Value of Pen: "
                           + properties
                                 .getOrDefault("Pen", 200));

        // Getting the value of Phone
        System.out.println("Value of Phone: "
                           + properties
                                 .getOrDefault("Phone", 200));
    }
}
```

**输出:**

```java
Properties: {Book=500, Mobile=5000, Pen=10, Clothes=400}
Value of Pen: 10
Value of Phone: 200

```

**程序二:**

```java
// Java program to demonstrate
// getOrDefault(key, defaultValue) method.

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

        // Getting the value of 1
        System.out.println("Value of 1: "
                           + properties
                                 .getOrDefault(1, "200RS"));

        // Getting the value of 5
        System.out.println("Value of 5: "
                           + properties
                                 .getOrDefault(5, "200RS"));
    }
}
```

**输出:**

```java
Current Properties: {3=1000RS, 2=500RS, 1=100RS}
Value of 1: 100RS
Value of 5: 200RS

```

参考文献:[https://docs . Oracle . com/javase/9/docs/API/Java/util/properties . html # getOrDefault-Java . lang . object-Java . lang . object-](https://docs.oracle.com/javase/9/docs/api/java/util/Properties.html#getOrDefault-java.lang.Object-java.lang.Object-)