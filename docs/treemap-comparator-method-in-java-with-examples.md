# Java 中的 TreeMap 比较器()方法，带示例

> 原文:[https://www . geesforgeks . org/tree map-comparator-in-Java-method-with-examples/](https://www.geeksforgeeks.org/treemap-comparator-method-in-java-with-examples/)

[**Java . util . treemap**](https://www.geeksforgeeks.org/treemap-in-java/)类的**比较器()**方法用于返回用于排序此地图中的键的比较器，如果此地图使用其键的自然排序，则返回 null。

```java
--> java.util Package
    --> TreeMap Class
        --> comparator() Method 
```

**语法:**

```java
public Comparator comparator()
```

**返回类型:**该方法返回用于对该地图中的关键点进行排序的**比较器**，如果该地图使用其关键点的自然排序，则返回 null。

> **注:** *下行方式*默认为自然排序。

**例 1:** 自然排序

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Illustrate comparator() Method
// for Natural Ordering (Descending Order)

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] argv) throws Exception
    {

        // Try block to check for exceptions
        try {

            // Creating an empty TreeMap by
            // creating object of NavigableMap
            NavigableMap<Integer, String> treemap
                = new TreeMap<Integer, String>();

            // Populating TreeMap
            // using put() method
            treemap.put(1, "one");
            treemap.put(2, "two");
            treemap.put(3, "three");
            treemap.put(4, "four");
            treemap.put(5, "five");

            // Printing the TreeMap
            System.out.println("TreeMap: " + treemap);

            // Getting used Comparator in the map
            // using comparator() method
            Comparator comp = treemap.comparator();

            // Printing the comparator value
            System.out.println("Comparator value: " + comp);
        }

        // Catch block to handle the exception
        catch (NullPointerException e) {

            // Display message if exception occurs
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
TreeMap: {1=one, 2=two, 3=three, 4=four, 5=five}
Comparator value: null
```

**示例 2:** 用于反向排序

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate comparator() Method
// for Reverse Ordering

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] argv) throws Exception
    {

        // Try block to check for exceptions
        try {

            // Creating an empty TreeMap
            NavigableMap<Integer, String> treemap
                = new TreeMap<Integer, String>(
                    Collections.reverseOrder());

            // Populating TreeMap
            // using put() method
            treemap.put(1, "one");
            treemap.put(2, "two");
            treemap.put(3, "three");
            treemap.put(4, "four");
            treemap.put(5, "five");

            // Printing the TreeMap
            System.out.println("TreeMap: " + treemap);

            // Getting used Comparator in the map
            // using comparator() method
            Comparator comp = treemap.comparator();

            // Printing the comparator value
            System.out.println("Comparator value: " + comp);
        }

        // Catch block to handle the exceptions
        catch (NullPointerException e) {

            // Display message if exception occurs
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
TreeMap: {5=five, 4=four, 3=three, 2=two, 1=one}
Comparator value: java.util.Collections$ReverseComparator@232204a1
```