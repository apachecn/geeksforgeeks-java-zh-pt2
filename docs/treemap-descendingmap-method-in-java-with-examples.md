# Java 中的树形图下降映射()方法，示例

> 原文:[https://www . geesforgeks . org/tree map-dependingmap-method-in-Java-with-examples/](https://www.geeksforgeeks.org/treemap-descendingmap-method-in-java-with-examples/)

**下行映射()**方法用于返回该映射中包含的映射的逆序视图。映射的逆序或降序是根据键的降序。该地图支持降序地图，因此对地图的更改会反映在降序地图中，反之亦然。

**声明语法:**

```
public NavigableMap<K,V> descendingMap()

```

*   **K :** 就是这张地图维护的按键类型。
*   **V :** 是映射值的类型。

**参数:**不可用

**返回值:**此地图的逆序或降序视图。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate descendingMap() method

import java.util.*;

public class Example1 {
    public static void main(String[] args)
    {

        // Declaring the tree map of Integer and String
        TreeMap<Integer, String> treemap
            = new TreeMap<Integer, String>();

        // Add the mappings to the tree map using put()
        treemap.put(2, "Two");
        treemap.put(16, "Sixteen");
        treemap.put(8, "Eight");
        treemap.put(6, "Six");
        treemap.put(10, "Ten");

        // store the descending order of mappings in dmap
        NavigableMap dmap = treemap.descendingMap();

        System.out.println("Reverse navigable map values: "
                           + dmap);
    }
}
```

**Output**

```
Reverse navigable map values: {16=Sixteen, 10=Ten, 8=Eight, 6=Six, 2=Two}

```

**例 2 :**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate descendingMap() method

import java.util.*;

public class Example2 {
    public static void main(String[] args)
    {

        // Declaring the tree map of Integer and String
        TreeMap<Integer, String> treemap
            = new TreeMap<Integer, String>();

        // Add the mappings to the tree map using put()
        treemap.put(11, "Abhishek Rout");
        treemap.put(9, "Akash Salvi");
        treemap.put(2, "Hemant Koul");
        treemap.put(8, "Vaibhav Kamble");
        treemap.put(6, "Sagar Joshi");
        treemap.put(10, "Onkar Dherange");
        treemap.put(7, "Rajwardhan Shinde");
        treemap.put(1, "Rahul Gavhane");
        treemap.put(4, "Abhishek Gadge");
        treemap.put(3, "Pratik Kulkarni");
        treemap.put(5, "Raviraj Bugge");

        // store the descending order of mappings in dmap
        NavigableMap dmap = treemap.descendingMap();

        // print the mappings
        System.out.println(
            "List of students in reverse order: " + dmap);
    }
}
```

**Output**

```
List of students in reverse order: {11=Abhishek Rout, 10=Onkar Dherange, 9=Akash Salvi, 8=Vaibhav Kamble, 7=Rajwardhan Shinde, 6=Sagar Joshi, 5=Raviraj Bugge, 4=Abhishek Gadge, 3=Pratik Kulkarni, 2=Hemant Koul, 1=Rahul Gavhane}

```