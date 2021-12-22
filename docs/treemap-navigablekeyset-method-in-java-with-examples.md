# Java 中的 TreeMap navigableKeySet()方法，带示例

> 原文:[https://www . geesforgeks . org/tree map-navigatablekeyset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/treemap-navigablekeyset-method-in-java-with-examples/)

[**Java . util . treemap**](https://www.geeksforgeeks.org/treemap-in-java/)类的**navigatableKeySet()**方法用于返回该地图中包含的键的 NavigableSet 视图。
集合的迭代器以升序返回键。集合由地图支持，因此对地图的更改会反映在集合中，反之亦然。如果在对集合进行迭代时修改了映射(通过迭代器自己的移除操作除外)，迭代的结果是未定义的。集合支持元素移除，通过迭代器移除、集合移除、全部移除、保留和清除操作从映射中移除相应的映射。它不支持 add 或 addAll 操作。
**语法:**

```
public NavigableSet navigableKeySet()
```

**返回值:**该方法返回该地图中关键点的**可导航集合视图**。
以下举例说明*navigatablekeyset()*方法
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// navigableKeySet() method
// for Integer value key

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of TreeMap<Integer, String>
            TreeMap<Integer, String>
                treemap = new TreeMap<Integer, String>();

            // populating tree map
            treemap.put(1, "One");
            treemap.put(2, "Two");
            treemap.put(3, "Three");
            treemap.put(4, "Four");
            treemap.put(5, "Five");

            // printing the TreeMap
            System.out.println("TreeMap: " + treemap);

            // getting navigable set view of the keys
            // using navigableKeySet() method
            NavigableSet<Integer>
                value = treemap.navigableKeySet();

            // printing the value
            System.out.println("Value is: " + value);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
TreeMap: {1=One, 2=Two, 3=Three, 4=Four, 5=Five}
Value is: [1, 2, 3, 4, 5]
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// navigableKeySet() method
// for String value key

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of TreeMap<Integer, String>
            TreeMap<String, Integer>
                treemap = new TreeMap<String, Integer>();

            // populating tree map
            treemap.put("A", 1);
            treemap.put("B", 2);
            treemap.put("C", 3);
            treemap.put("D", 4);
            treemap.put("E", 5);

            // printing the TreeMap
            System.out.println("TreeMap: " + treemap);

            // getting navigable set view of the keys
            // using navigableKeySet() method
            NavigableSet<String>
                value = treemap.navigableKeySet();

            // printing the value
            System.out.println("Value is: " + value);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
TreeMap: {A=1, B=2, C=3, D=4, E=5}
Value is: [A, B, C, D, E]
```