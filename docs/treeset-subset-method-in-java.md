# Java 中的 TreeSet subSet()方法

> 原文:[https://www . geesforgeks . org/treeset-subset-method-in-Java/](https://www.geeksforgeeks.org/treeset-subset-method-in-java/)

java.util.TreeSet.subSet()用于返回参数中提到的范围内现有 TreeSet 的子集。该方法接受一个上限和一个下限，并返回该范围内提到的所有元素。如果元素存在于集合中，则包括下限，而排除上限。基本上，它取大于等于下限且严格小于上限的子集。

**语法:**

```
*TreeSet* tree_set.subSet(Object low_element, Object up_element)
```

**参数:**

*   *low_element:* 这是 TreeSet 的类型，定义了评估子集的下限或起始元素。该元素包含在子集中。
*   *up_element:* 这是 TreeSet 的类型，定义了子集评估的上限或最后一个元素。此元素被排除在子集之外。

**返回值:**该方法返回给定参数范围内提到的 TreeSet 类型的子集。

下面的程序说明了 Java . util . TreeSet . SubIt()方法:

**程序 1** :

```
// Java code to illustrate subSet() method
import java.io.*;
import java.util.Iterator;
import java.util.TreeSet;

public class Tree_Set_Demo {
    public static void main(String[] args)
    {

        // Creating an empty TreeSet
        TreeSet<Integer> tree_set = new TreeSet<Integer>();

        // Adding the elements using add()
        tree_set.add(5);
        tree_set.add(1);
        tree_set.add(50);
        tree_set.add(10);
        tree_set.add(20);
        tree_set.add(6);
        tree_set.add(20);
        tree_set.add(18);
        tree_set.add(9);
        tree_set.add(30);

        // Creating the subset tree
        TreeSet<Integer> sub_set = new TreeSet<Integer>();

        // Limiting the values till 5
        sub_set = (TreeSet<Integer>)tree_set.subSet(6, 30);

        // Creating an Iterator
        Iterator iterate;
        iterate = sub_set.iterator();

        // Displaying the tree set data
        System.out.println("The resultant values within the sub set: ");

        // Iterating through the subset
        while (iterate.hasNext()) {
            System.out.println(iterate.next() + " ");
        }
    }
}
```

**Output:**

```
The resultant values within the sub set: 
6 
9 
10 
18 
20

```

**程序 2** :

```
// Java code to illustrate subSet() method when TreeSet
// contains elements of String type
import java.io.*;
import java.util.Iterator;
import java.util.TreeSet;

public class Tree_Set_Demo {
    public static void main(String[] args)
    {

        // Creating an empty TreeSet
        TreeSet<String> tree_set = new TreeSet<String>();

        // Adding the elements using add()
        tree_set.add("Welcome");
        tree_set.add("To");
        tree_set.add("Geek");
        tree_set.add("4");
        tree_set.add("Geeks");
        tree_set.add("TreeSet");

        // Creating the subset tree
        TreeSet<String> sub_set = new TreeSet<String>();

        // Limiting the values till 5
        sub_set = (TreeSet<String>)tree_set.subSet("4", "TreeSet");

        // Creating an Iterator
        Iterator iterate;
        iterate = sub_set.iterator();

        // Displaying the tree set data
        System.out.println("The resultant values within the sub set: ");

        // Iterating through the subset
        while (iterate.hasNext()) {
            System.out.println(iterate.next() + " ");
        }
    }
}
```

**Output:**

```
The resultant values within the sub set: 
4 
Geek 
Geeks 
To

```