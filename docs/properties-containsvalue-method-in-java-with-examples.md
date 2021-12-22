# 属性包含 Java 中的(值)方法，示例

> 原文:[https://www . geesforgeks . org/properties-contains-value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/properties-containsvalue-method-in-java-with-examples/)

**包含 **[属性类](https://www.geeksforgeeks.org/java-util-properties-class-java/)** 的(值)**方法用于检查该属性对象是否包含该值对其中任何键的映射。它将该值作为参数进行比较，并返回一个布尔值作为结果。此方法比 containsKey()方法更昂贵。此外，此方法在工作中与 containsValue()方法相同。

**语法:**

```
public Object contains(Object value)
```

**参数:**该方法接受一个参数**值**，该值是要在该属性中搜索的值。

**返回:**该方法返回一个**布尔值**，说明该值是否存在于该属性对象中。

下面的程序说明了 contains(值)方法:

**程序 1:**

```
// Java program to demonstrate
// contains(value) method.

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

        // Check if 10 is present or not
        // using contains()
        System.out.println("Is 10 present: "
                           + properties.contains(10));
    }
}
```

**输出:**

```
Current Properties: {Book=500, Mobile=5000, Pen=10, Clothes=400}
Is 10 present: true

```

**程序二:**

```
// Java program to demonstrate
// contains(value) method.

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

        // print Properties details
        System.out.println("Current Properties: "
                           + properties.toString());

        // Check if 200RS is present or not
        // using contains()
        System.out.println("Is 200RS present: "
                           + properties.contains("200RS"));
    }
}
```

**输出:**

```
Current Properties: {3=1000RS, 2=500RS, 1=100RS}
Is 200RS present: false

```

参考文献:[https://docs . Oracle . com/javase/9/docs/API/Java/util/properties . html # contains-Java . lang . object-](https://docs.oracle.com/javase/9/docs/api/java/util/Properties.html#contains-java.lang.Object-)