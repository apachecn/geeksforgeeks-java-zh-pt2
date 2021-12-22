# Java 中的 TreeMap ceilingEntry()和 ceilingKey()方法

> 原文:[https://www . geesforgeks . org/tree map-ceilingentry-and-ceiling key-methods-in-Java/](https://www.geeksforgeeks.org/treemap-ceilingentry-and-ceilingkey-methods-in-java/)

Java.util.TreeMap 中有两个 ceilingEntry()的**变体，本文将对这两个变体进行讨论。**

****1。ceilingEntry(K 键):**用于返回与大于或等于给定键的最小键**相关联的**键值映射**，如果没有这样的键，则返回**或 null。**

```java
**Syntax :** 
**public Map.Entry ceilingEntry(K key)**
**Parameters :** 
**key :** The key to be matched.
**Return Value :** 
It returns the entry with the least key greater than or equal to key, and null if 
there is no such key.
**Exception :** 
**ClassCastException :** It throws the exception if the specified key cannot be compared
with the keys currently in the map.
**NullPointerException :** It throws the exception if the specified key is null. 
```

```java
// Java code to demonstrate the working of 
// ceilingEntry()

import java.io.*;
import java.util.*;

public class ceilingEntry1 {

  public static void main(String[] args) {

  // Declaring the tree map of Integer and String
  TreeMap<Integer, String> treemap = new TreeMap<Integer, String>();

  // assigning the values in the tree map
  // using put()
  treemap.put(2, "two");
  treemap.put(7, "seven");
  treemap.put(3, "three");

  // Use of ceilingEntry()
  // returns 7=seven ( next greater key-value)
  System.out.println("The next greater key-value of 5 is : " + treemap.ceilingEntry(5));

  // returns "null" as no value present
  // greater than or equal to number
  System.out.println("The next greater key-value of 8 is : " + treemap.ceilingEntry(8));

  }
}
```

**输出:**

```java
The next greater key-value of 5 is : 7=seven
The next greater key-value of 8 is : null 
```

****2。ceilingKey(K key) :** 这个也和上面那个有相同的工作，但是唯一的区别是**它不包含映射键**。它只返回大于或等于给定键的最小键，否则返回空值。**

```java
**Syntax :** 
public K ceilingKey(K key)
**Parameters :** 
**key :** The key to be matched.
**Return Value :** 
It returns the entry with the least key greater than or equal to key, and null 
if there is no such key.
**Exception:**
**ClassCastException :** It throws the exception if the specified key cannot be compared
with the keys currently in the map.
**NullPointerException :** It throws the exception if the specified key is null. 
```

```java
// Java code to demonstrate the working of 
// ceilingKey()

import java.io.*;
import java.util.*;

public class ceilingKey1 {

  public static void main(String[] args) {

  // Declaring the tree map of Integer and String
  TreeMap<Integer, String> treemap = new TreeMap<Integer, String>();

  // assigning the values in the tree map
  // using put()
  treemap.put(2, "two");
  treemap.put(7, "seven");
  treemap.put(3, "three");

  // Use of ceilingKey()
  // returns 7 ( next greater key)
  System.out.println("The next greater key of 5 is : " + treemap.ceilingKey(5));

  // returns "null" as no key present
  // greater than or equal to number
  System.out.println("The next greater key of 8 is : " + treemap.ceilingKey(8));

  }
}
```

**输出:**

```java
The next greater key of 5 is : 7
The next greater key of 8 is : null 
```

**本文由**香巴拉维·辛格**T2 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。**

**如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**