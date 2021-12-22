# Java 中 TreeMap 和 TreeSet 的相似之处

> 原文:[https://www . geesforgeks . org/tree map-and-treeset-in-Java/](https://www.geeksforgeeks.org/similarities-between-treemap-and-treeset-in-java/)之间的相似之处

[**TreeSet**](https://www.geeksforgeeks.org/treeset-in-java-with-examples/#:~:text=TreeSet%20implements%20the%20SortedSet%20interface,elements%20are%20sorted%20by%20keys.) 主要是 java 中 SortedSet 的一个实现，不允许重复，对象以排序和升序的方式存储。

[**树状图**](https://www.geeksforgeeks.org/treemap-in-java/)**是地图界面的一个实现。树地图也是导航地图和抽象地图类的实现。**

****Java 中 TreeSet 和 TreeMap 的相似之处。****

1.  **TreeMap 和 TreeSet 都属于 java.util 包。**
***   Both are part of the Java collection framework.*   Null values are not allowed.*   Both are sorted. The sort order can be either the natural sort order defined by the comparable interface or the custom sort order defined by the comparison interface.*   They are not synchronized, so they are not used for concurrent applications.*   Both of them provide O(log(n)) time complexity for any operation (such as put, get, containsKey, remove).*   Red-black trees are used inside sets and tree diagrams.**

****tree map 和 TreeSet 图解:****

## **Java**

```java
// Java program to demonstrate some basic functions
// of TreeMap and TreeSet

import java.util.*;
import java.io.*;

class GFG {
    public static void main (String[] args) {

      TreeSet<Integer> st=new TreeSet<>();
      st.add(4);
      st.add(5);
      st.add(6);
      st.add(8);
      st.add(4);

      TreeMap<Integer,Integer> tm=new TreeMap<>();
      tm.put(2,5);
      tm.put(3,6);
      tm.put(4,6);
      tm.put(2,3);

      System.out.println(st);
      System.out.println(tm);

    }
}
```

****输出**

```java
[4, 5, 6, 8]
{2=3, 3=6, 4=6}
```**