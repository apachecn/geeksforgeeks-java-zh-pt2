# 属性包含 Java 中的键(值)方法，示例

> 原文:[https://www . geesforgeks . org/properties-contains key value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/properties-containskeyvalue-method-in-java-with-examples/)

**包含键(值)****[属性类](https://www.geeksforgeeks.org/java-util-properties-class-java/)** 的方法用于检查该属性对象是否包含该键对其中任何键的映射。它将该值作为参数进行比较，并返回一个布尔值作为结果。

**语法:**

```
public Object containsKey(Object value)
```

**参数:**该方法接受一个参数**值**，该值是该属性中要搜索的关键字。

**返回:**该方法返回一个**布尔值**，说明该属性对象中是否存在该键的结果。

下面的程序说明了 containsKey(值)方法:

**程序 1:**

```
// Java program to demonstrate
// containsKey(value) method.

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

        // Check if Pen is present or not
        // using containsKey()
        System.out.println("Is Pen present: "
                           + properties.containsKey("Pen"));
    }
}
```

**输出:**

```
Current Properties: {Book=500, Mobile=5000, Pen=10, Clothes=400}
Is Pen present: true

```

**程序二:**

```
// Java program to demonstrate
// containsKey(value) method.

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

        // Check if 5 is present or not
        // using containsKey()
        System.out.println("Is 5 present: "
                           + properties.containsKey(5));
    }
}
```

**输出:**

```
Current Properties: {3=1000RS, 2=500RS, 1=100RS}
Is 5 present: false

```

参考文献:[https://docs . Oracle . com/javase/9/docs/API/Java/util/properties . html # contains key-Java . lang . object-](https://docs.oracle.com/javase/9/docs/api/java/util/Properties.html#containsKey-java.lang.Object-)