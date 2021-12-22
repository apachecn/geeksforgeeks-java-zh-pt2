# Java 中的 TreeSet lower()方法

> 原文:[https://www.geeksforgeeks.org/treeset-lower-method-in-java/](https://www.geeksforgeeks.org/treeset-lower-method-in-java/)

Java 中 TreeSet 类的 **lower(E ele)** 方法用来返回这个集合中最大的元素，这个元素严格小于给定的元素。如果这个树集合中不存在这样的元素，那么这个方法返回一个空值。

这里，E 是这个集合维护的元素的类型。

**语法** :

```java
public E lower(E ele)
```

**参数:**只需要一个参数 **ele** 。它是确定集合中严格小于该值的最大值的元素。

**返回值:**它返回一个类型为 E 的值，该值为空或所需值。

**异常:**

*   [T0】 ClassCastException 【T1]: If the specified element cannot be compared with the elements of the collection, this method throws a class castexception.
*   [T0】 NullPointRexception 【T1]: If the given element is empty, and the set uses natural sorting or the comparator does not allow null values, this method throws NullPointRexception.

下面的程序说明了 lower()方法:

**节目 1** :

```java
// Java program to illustrate lower() method
// of TreeSet class

import java.util.TreeSet;
public class GFG {
    public static void main(String args[])
    {
        TreeSet<Integer> tree = new TreeSet<Integer>();

        // Add elements to this TreeSet
        tree.add(10);
        tree.add(5);
        tree.add(8);
        tree.add(1);
        tree.add(11);
        tree.add(3);

        System.out.println(tree.lower(15));
    }
}
```

**输出** :

```java
11

```

**程序 2** (空指针异常演示):

```java
// Java program to illustrate lower() method
// of TreeSet class

import java.util.TreeSet;
public class GFG {
    public static void main(String args[])
    {
        TreeSet<String> tree = new TreeSet<String>();

        try {

            // Add elements to TreeSet
            tree.add("10");
            tree.add("5");
            tree.add("8");
            tree.add("1");
            tree.add("11");
            tree.add("3");

            System.out.println(tree.lower(null));
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**输出** :

```java
java.lang.NullPointerException
    at java.util.TreeMap.compare(TreeMap.java:1294)
    at java.util.TreeMap.getLowerEntry(TreeMap.java:494)
    at java.util.TreeMap.lowerKey(TreeMap.java:711)
    at java.util.TreeSet.lower(TreeSet.java:414)
    at GFG.main(GFG.java:20)

```

**程序 3** (阶级例外演示):

```java
// Java program to illustrate lower() method
// of TreeSet class

import java.util.ArrayList;
import java.util.LinkedList;
import java.util.List;
import java.util.TreeSet;

public class GFG {
    public static void main(String args[])
    {
        TreeSet<List> tree = new TreeSet<List>();

        List<Integer> l1 = new LinkedList<Integer>();
        l1.add(1);
        l1.add(2);
        tree.add(l1);

        List<Integer> l2 = new LinkedList<Integer>();
        l2.add(3);
        l2.add(4);

        List<Integer> l3 = new ArrayList<Integer>();
        l2.add(5);
        l2.add(6);

        try {
            System.out.println(tree.lower(l3));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出** :

```java
Exception in thread "main" java.lang.ClassCastException: 
java.util.LinkedList cannot be cast to java.lang.Comparable
    at java.util.TreeMap.compare(TreeMap.java:1294)
    at java.util.TreeMap.put(TreeMap.java:538)
    at java.util.TreeSet.add(TreeSet.java:255)
    at GFG.main(GFG.java:17)

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/treeset . html # lower(E)](https://docs.oracle.com/javase/7/docs/api/java/util/TreeSet.html#lower(E))