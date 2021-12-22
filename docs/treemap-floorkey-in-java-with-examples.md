# Java 中的树形图布局键()，示例

> 原文:[https://www . geesforgeks . org/tree map-floor key-in-Java-with-examples/](https://www.geeksforgeeks.org/treemap-floorkey-in-java-with-examples/)

**先决条件:**[Java 中的树形图](https://www.geeksforgeeks.org/treemap-in-java/)

**钻取键()**方法用于从参数中返回小于或等于给定键的最大键。

**语法:**

```
public K floorKey(K key)
```

**参数:**此方法接受一个强制参数*键*，它是要匹配的键。

**返回值:**方法调用返回*小于或等于键*的最大键，如果没有这样的键则返回 **null** 。

**异常:**该方法抛出以下异常:

*   **ClassCastException** :当指定的键无法与地图中可用的键进行比较时。
*   **NullPointRexception**:当映射中指定的键为空并且使用自然的
    排序时，这意味着比较器不允许空键。

以下是举例说明如何使用 floorKey()方法:

**例 1:**

```
// Java program to demonstrate floorKey() method

import java.util.TreeMap;

public class FloorKeyDemo {
    public static void main(String args[])
    {

        // create an empty TreeMap
        TreeMap<Integer, String> numMap = new TreeMap<Integer, String>();

        // Insert the values
        numMap.put(6, "Six");
        numMap.put(1, "One");
        numMap.put(5, "Five");
        numMap.put(3, "Three");
        numMap.put(8, "Eight");
        numMap.put(10, "Ten");

        // Print the Values of TreeMap
        System.out.println("TreeMap: " + numMap.toString());

        // Get the greatest key mapping of the Map

        // As here 11 is not available it returns 10
        // because ten is less than 11
        System.out.print("Floor Entry of Element 11 is: ");
        System.out.println(numMap.floorKey(11));

        // This will give null
        System.out.print("Floor Entry of Element 0 is: ");
        System.out.println(numMap.floorKey(0));
    }
}
```

**Output:**

```
TreeMap: {1=One, 3=Three, 5=Five, 6=Six, 8=Eight, 10=Ten}
Floor Entry of Element 11 is: 10
Floor Entry of Element 0 is: null

```

**示例 2:** 演示空指针异常

```
// Java program to demonstrate floorKey() method

import java.util.TreeMap;

public class FloorKeyDemo {
    public static void main(String args[])
    {

        // create an empty TreeMap
        TreeMap<Integer, String>
            numMap = new TreeMap<Integer, String>();

        // Insert the values
        numMap.put(6, "Six");
        numMap.put(1, "One");
        numMap.put(5, "Five");
        numMap.put(3, "Three");
        numMap.put(8, "Eight");
        numMap.put(10, "Ten");

        // Print the Values of TreeMap
        System.out.println("TreeMap: " + numMap.toString());

        try {
            // Passing null as parameter to floorKey()
            // This will throw exception
            System.out.println(numMap.floorKey(null));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```
TreeMap: {1=One, 3=Three, 5=Five, 6=Six, 8=Eight, 10=Ten}
Exception: java.lang.NullPointerException

```