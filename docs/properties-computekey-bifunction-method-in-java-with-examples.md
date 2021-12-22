# Java 中属性计算(键、双功能)方法，示例

> 原文:[https://www . geesforgeks . org/properties-computekey-bifunction-method-in-Java-with-examples/](https://www.geeksforgeeks.org/properties-computekey-bifunction-method-in-java-with-examples/)

**属性类**的**计算(键，双功能)**方法允许计算指定键及其当前映射值的映射(如果没有找到当前映射，则为空)。

*   If the remapping function passed in the Properties' compute () returns null as the return value, the mapping is removed from the Properties (or if it does not exist at first, it does not exist).
*   If the remapping function throws an exception, it throws an exception again, and the current mapping remains unchanged.
*   This method is not allowed to modify the map during the calculation.
*   If the remapping function modifies the mapping during the calculation, this method will throw **Concurrentmodification Exception** .

**语法:**

```java
public Object compute?(Object key,
                      BiFunction remappingFunction)
```

**参数:**此方法接受两个参数:

*   **key** : the key with which the value is to be associated.
*   [T0】 remapingfunction 【T1]: the function of computing numerical values.

**返回:**该方法返回与指定键关联的**新值，如果没有则返回空值**。

**异常:**如果检测到重映射函数修改了该地图，则该方法抛出**ConcurrentModificationException**。

以下程序说明了计算(键，双功能)方法:

**程序 1:**

```java
// Java program to demonstrate
// compute(Key, BiFunction) method.

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

        // remap the values of Properties
        // using compute method
        properties.compute("Pen", (key, val)
                                      -> 15);
        properties.compute("Clothes", (key, val)
                                          -> 120);

        // print new mapping
        System.out.println("New Properties: "
                           + properties.toString());
    }
}
```

**输出:**

```java
Current Properties: {Book=500, Mobile=5000, Pen=10, Clothes=400}
New Properties: {Book=500, Mobile=5000, Pen=15, Clothes=120}

```

**程序二:**

```java
// Java program to demonstrate
// compute(Key, BiFunction) method.

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

        // remap the values of Properties
        // using compute method
        properties.compute(3, (key, val)
                                  -> "00RS");
        properties.compute(2, (key, val)
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
New Properties: {3=00RS, 2=$, 1=100RS}

```

参考文献:[https://docs . Oracle . com/javase/9/docs/API/Java/util/properties . html # compute-Java . lang . object-Java . util . function . bifunction-](https://docs.oracle.com/javase/9/docs/api/java/util/Properties.html#compute-java.lang.Object-java.util.function.BiFunction-)