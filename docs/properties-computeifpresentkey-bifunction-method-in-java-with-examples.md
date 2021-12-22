# 属性计算 Java 中的 Present(Key，BiFunction)方法，示例

> 原文:[https://www . geeksforgeeks . org/properties-computeifpresentkey-bifunction-method-in-Java-with-examples/](https://www.geeksforgeeks.org/properties-computeifpresentkey-bifunction-method-in-java-with-examples/)

**属性类**的**计算当前(键，双功能)**方法，如果键已经与值相关联(或映射为空)，则允许您计算指定键的映射值。

*   If the mapping function of this method returns null, the mapping is removed.
*   If the remapping function throws an exception, it throws an exception again, and the mapping remains unchanged.
*   This method is not allowed to modify the map during the calculation.
*   If the remapping function modifies this mapping during calculation, this method will throw a Concurrentmodification Exception.

**语法:**

```java
public Object computeIfPresent?(Object key,
                              BiFunction remappingFunction)
```

**参数:**此方法接受两个参数:

*   **key** : the key with which the value is to be associated.
*   [T0】 remapingfunction 【T1]: the function of computing numerical values.

**返回:**该方法返回与指定键关联的**新的重映射值，如果映射返回空值**，则返回空值。

**异常:**如果检测到重映射函数修改了该地图，则该方法抛出**ConcurrentModificationException**。

下面的程序说明了计算呈现(键，双功能)方法:

**程序 1:**

```java
// Java program to demonstrate
// computeIfPresent(Key, BiFunction) method.

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

        // provide new value for keys which is present
        // using computeIfPresent method
        properties.computeIfPresent("Pen", (key, val)
                                               -> 600);
        properties.computeIfPresent("Book", (key, val)
                                                -> 800);

        // print new mapping
        System.out.println("New Properties: "
                           + properties.toString());
    }
}
```

**输出:**

```java
Current Properties: {Book=500, Mobile=5000, Pen=10, Clothes=400}
New Properties: {Book=800, Mobile=5000, Pen=600, Clothes=400}

```

**程序二:**

```java
// Java program to demonstrate
// computeIfPresent(Key, BiFunction) method.

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

        // provide new value for key which is present
        // using computeIfPresent method
        properties.computeIfPresent(3, (key, val)
                                           -> "00RS");

        // this will not effect anything
        // because key 4 is absent
        properties.computeIfPresent(4, (key, val)
                                           -> "{content}quot;);

        // print new mapping
        System.out.println("New Properties: "
                           + properties.toString());
    }
}
```

**输出:**

```java
Current Properties: {3=1000RS, 2=500RS, 1=100RS}
New Properties: {3=00RS, 2=500RS, 1=100RS}

```

参考文献:[https://docs . Oracle . com/javase/9/docs/API/Java/util/properties . html # computeIfPresent-Java . lang . object-Java . util . function . bifunction-](https://docs.oracle.com/javase/9/docs/api/java/util/Properties.html#computeIfPresent-java.lang.Object-java.util.function.BiFunction-)