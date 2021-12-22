# Java 中的 TreeMap higherEntry()方法，带示例

> 原文:[https://www . geesforgeks . org/tree map-higher entry-method-in-Java-with-examples/](https://www.geeksforgeeks.org/treemap-higherentry-method-in-java-with-examples/)

[**Java . util . treemap**](https://www.geeksforgeeks.org/treemap-in-java/)类的 **higherEntry()** 方法用于返回与严格大于给定键的最小键相关联的键值映射，如果没有这样的键，则返回 null。
**语法:**

```java
public Map.Entry higherEntry(K key)
```

**参数:**该方法以**键**为参数。
**返回值:**该方法返回一个最少键大于键的条目，如果没有这样的键则**为空**。
**异常:**如果指定的键为空，并且该映射使用自然排序，或者其比较器不允许空键，则该方法抛出**空指针异常**。
以下是举例说明 *higherEntry()* 方法
T20】例 1:T22】

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// higherEntry() method
// for <Integer, String> value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
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

            // getting higher entry value fro 3
            Map.Entry<Integer, String>
                value
                = treemap.higherEntry(3);

            // printing the value
            System.out.println("The higherEntry value "
                               + " for 3: " + value);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
TreeMap: {1=One, 2=Two, 3=Three, 4=Four, 5=Five}
The higherEntry value  for 3: 4=Four
```

**例 2:** 为**零点异常**T4】

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// higherEntry() method
// for NullPointerException

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
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

            // getting higher entry value fro null
            System.out.println("Trying to get "
                               + "the higher entry value"
                               + " for null");

            Map.Entry<Integer, String>
                value
                = treemap.higherEntry(null);

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

```java
TreeMap: {1=One, 2=Two, 3=Three, 4=Four, 5=Five}
Trying to get the higher entry value for null
Exception thrown : java.lang.NullPointerException
```