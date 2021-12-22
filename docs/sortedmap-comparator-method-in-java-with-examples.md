# Java 中 SortedMap 比较器()方法示例

> 原文:[https://www . geesforgeks . org/sorted map-comparator-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedmap-comparator-method-in-java-with-examples/)

**java.util.SortedMap** 接口的**比较器()**方法用于返回用于对该地图中的键进行排序的比较器，如果该地图使用其键的自然排序，则返回 null。
**语法:**

```java
public Comparator comparator()
```

**返回值:**该方法返回用于对该地图中的关键点进行排序的**比较器**，如果该地图使用其关键点的自然排序，则返回 null。
下面的程序说明了**比较器()**方法:
**例 1:** 为自然排序。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// comparator() method for natural ordering

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // Creating object of SortedTreeMap
            SortedMap<Integer, String>
                sotreemap = new TreeMap<Integer, String>();

            // Populating tree map
            sotreemap.put(1, "one");
            sotreemap.put(2, "two");
            sotreemap.put(3, "three");
            sotreemap.put(4, "four");
            sotreemap.put(5, "five");

            // Printing the SortedTreeMap
            System.out.println("SortedTreeMap: " + sotreemap);

            // Getting used Comparator in the map
            // using comparator() method
            Comparator comp = sotreemap.comparator();

            // Printing the comparator value
            System.out.println("Comparator value: "
                               + comp);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
SortedTreeMap: {1=one, 2=two, 3=three, 4=four, 5=five}
Comparator value: null
```

**例 2:** 为逆序。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// comparator() method
// for reverse ordering

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception<div class="code-output">
<b>Output:</b>
<pre>
Initial Mappings are: {10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You}
The set is: [10=Geeks, 15=4, 20=Geeks, 25=Welcomes, 30=You]
</pre>
</div>

    {

        try {

            // Creating object of TreeMap
            SortedMap<Integer, String>
                sotreemap = new TreeMap<Integer, String>(
                    Collections.reverseOrder());

            // Populating tree map
            sotreemap.put(1, "one");
            sotreemap.put(2, "two");
            sotreemap.put(3, "three");
            sotreemap.put(4, "four");
            sotreemap.put(5, "five");

            // Printing the TreeMap
            System.out.println("SortedTreeMap: " + sotreemap);

            // Getting used Comparator in the map
            // using comparator() method
            Comparator comp = sotreemap.comparator();

            // Printing the comparator value
            System.out.println("Comparator value: " + comp);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
SortedTreeMap: {5=five, 4=four, 3=three, 2=two, 1=one}
Comparator value: java.util.Collections$ReverseComparator@232204a1
```