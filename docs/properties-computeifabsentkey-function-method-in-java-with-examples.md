# 属性计算 Java 中缺少的(键、函数)方法，示例

> 原文:[https://www . geeksforgeeks . org/properties-computeifexkey-function-method-in-Java-with-examples/](https://www.geeksforgeeks.org/properties-computeifabsentkey-function-method-in-java-with-examples/)

**属性类**的**计算缺少(键，函数)**方法，如果键还没有与值相关联(或被映射为空)，该方法允许您计算指定键的映射值。

*   If the mapping function of this method returns null, the mapping is not recorded.
*   If the remapping function throws an exception, it throws an exception again and records the no mapping.
*   This method is not allowed to modify the map during the calculation.
*   If the remapping function modifies this mapping during calculation, this method will throw a Concurrentmodification Exception.

**语法:**

```
public Object computeIfAbsent?(Object key,
                              Function mappingFunction)
```

**参数:**此方法接受两个参数:

*   **key** : the key with which the value is to be associated.
*   [T0】 remapingfunction 【T1]: the function of computing numerical values.

**返回:**此方法返回**与指定键关联的当前(现有或计算的)值，如果映射返回空值**，则返回空值。

**异常:**如果检测到重映射函数修改了该地图，则该方法抛出**ConcurrentModificationException**。

以下程序说明了计算无(键，函数)方法:

**程序 1:**

```
// Java program to demonstrate
// computeIfAbsent(Key, Function) method.

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

        // print Properties details
        System.out.println("Current Properties: "
                           + properties.toString());

        // provide value for new key which is absent
        // using computeIfAbsent method
        properties.computeIfAbsent("newPen", k -> 600);
        properties.computeIfAbsent("newBook", k -> 800);

        // print new mapping
        System.out.println("New Properties: "
                           + properties.toString());
    }
}
```

**输出:**

```
Current Properties: {Book=500, Mobile=5000, Pen=10, Clothes=400}
New Properties: {newPen=600, Book=500, newBook=800, Mobile=5000, Pen=10, Clothes=400}

```

**程序二:**

```
// Java program to demonstrate
// computeIfAbsent(Key, Function) method.

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

        // provide value for new key which is absent
        // using computeIfAbsent method
        properties.computeIfAbsent(4, k -> "600RS");

        // this will not effect anything
        // because key 1 is present
        properties.computeIfAbsent(1, k -> "800RS");

        // print new mapping
        System.out.println("New Properties: "
                           + properties.toString());
    }
}
```

**输出:**

```
Current Properties: {3=1000RS, 2=500RS, 1=100RS}
New Properties: {4=600RS, 3=1000RS, 2=500RS, 1=100RS}

```

参考文献:[https://docs . Oracle . com/javase/9/docs/API/Java/util/properties . html #computeif 缺席-Java . lang . object-Java . util . function . function-](https://docs.oracle.com/javase/9/docs/api/java/util/Properties.html#computeIfAbsent-java.lang.Object-java.util.function.Function-)