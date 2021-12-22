# Java 中的属性 entrySet()方法，示例

> 原文:[https://www . geesforgeks . org/properties-entryset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/properties-entryset-method-in-java-with-examples/)

**[属性类](https://www.geeksforgeeks.org/java-util-properties-class-java/)** 的 **entrySet()** 方法用于获取该属性映射的 Set 视图。

**语法:**

```
public Set<Map.Entry> entrySet()
```

**参数:**该方法不接受任何参数。

**返回:**该方法返回该属性对象的映射的**集**视图。

下面的程序说明了 entrySet()方法:

**程序 1:**

```
// Java program to demonstrate
// entrySet() method.

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

        // Using entrySet() to get the set view
        System.out.println("The set is: "
                           + properties.entrySet());
    }
}
```

**输出:**

```
Current Properties: {Book=500, Mobile=5000, Pen=10, Clothes=400}
The set is: [Book=500, Mobile=5000, Pen=10, Clothes=400]

```

**程序二:**

```
// Java program to demonstrate
// entrySet() method.

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

        // Using entrySet() to get the set view
        System.out.println("The set is: "
                           + properties.entrySet());
    }
}
```

**输出:**

```
Current Properties: {3=1000RS, 2=500RS, 1=100RS}
The set is: [3=1000RS, 2=500RS, 1=100RS]

```

参考资料:[https://docs . Oracle . com/javase/9/docs/API/Java/util/properties . html # entrySet–](https://docs.oracle.com/javase/9/docs/api/java/util/Properties.html#entrySet--)