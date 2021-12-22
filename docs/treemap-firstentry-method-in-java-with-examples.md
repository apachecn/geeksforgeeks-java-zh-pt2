# Java 中的 TreeMap firstEntry()方法，带示例

> 原文:[https://www . geesforgeks . org/tree map-first entry-method-in-Java-with-examples/](https://www.geeksforgeeks.org/treemap-firstentry-method-in-java-with-examples/)

**TreeMap firstEntry()** 指的是用于检索与 TreeMap 中存在的最低键值元素映射的键值对的方法，如果 Map 中没有键值对，则简单返回 null。方法名**‘first entry()’**解释了它将返回具有最少键值的条目。

```java
Syntax: public Map.Entry<K,V> firstEntry(), 

Here K and V refer key-value respectively.

Parameters: NA - As it doesnot accept any parameter.

Return Value: It returns an entry with the least key (lowest key-value pair) and null if the 
TreeMap is empty.

Exception: NA - As it doesnot throw any exception at entry return.

```

### 例 1:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to demonstrate 
// the working of TreeMap firstKey() 
import java.io.*; 
import java.util.*; 
public class treeMapFirstKey { 
public static void main(String[] args) 
    { 

        // Declaring the TreeMap of Key - Value Pairs
        // Integer - Key , String - Value
        TreeMap<Integer, String> treemap = new TreeMap<Integer, String>(); 

        // Adding-up the values in the TreeMap 
        // Use put() function to append data 
        treemap.put(2, "Java"); 
        treemap.put(4, "CPP"); 
        treemap.put(5, "PHP"); 
        treemap.put(1, "Python"); 
        treemap.put(3, "C"); 

        // Check for firstEntry()
        System.out.println("Lowest Entry is: " + treemap.firstEntry()); 
    } 
}
```

**Output**

```java
Lowest Entry is: 1=Python

```

通过上面的例子，很明显 firstEntry()检查比较了 TreeMap 的每个键，并返回具有最少键值对的值。

### 例 2:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to demonstrate the working
// of TreeMap firstKey() method
import java.io.*; 
import java.util.*; 
public class percentageFirstKey { 
public static void main(String[] args) 
    { 

        // Declaring the TreeMap of Key - Value Pairs
        // Double - Key , String - Value
        TreeMap<Double, String> treemapPercentage = new TreeMap<Double, String>(); 

        // Adding-up the values in the TreeMap 
        // Use put() function to append data 
        treemapPercentage.put(81.40, "Shashank"); 
        treemapPercentage.put(72.80, "Anand");
        treemapPercentage.put(65.50, "Gulshan");
        treemapPercentage.put(71.10, "Abhishek"); 
        treemapPercentage.put(70.20, "Ram"); 

        // Check for firstEntry()
        System.out.println("Lowest Entry is: " + treemapPercentage.firstEntry()); 
    } 
}
```

**Output**

```java
Lowest Entry is: 65.5=Gulshan

```

**tree map first entry()上的一些点:**

*   TreeMap firstEntry()在 java.util 包中可用。
*   它不会在返回条目时引发异常。
*   TreeMap firstEntry()方法是一个非静态方法，因为它可以被类的对象访问，除此之外，还会得到一个错误。