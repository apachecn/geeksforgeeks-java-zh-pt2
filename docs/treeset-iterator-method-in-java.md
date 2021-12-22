# Java 中的 TreeSet 迭代器()方法

> 原文:[https://www . geesforgeks . org/treeset-iterator-method-in-Java/](https://www.geeksforgeeks.org/treeset-iterator-method-in-java/)

Java.util.TreeSet.iterator()方法用于返回与 TreeSet 相同元素的迭代器。元素从树集合中随机返回。

**语法:**

```
Iterator *iterate_value* = Tree_Set.iterator();

```

**参数:**函数不取任何参数。

**返回值:**该方法迭代树集合的元素并返回值(迭代器)。

下面程序举例说明了使用 Java.util.TreeSet.iterator()方法:

```
// Java code to illustrate iterator()
import java.util.*;
import java.util.TreeSet;

public class TreeSetDemo {
    public static void main(String args[])
    {
        // Creating an empty TreeSet
        TreeSet<String> set = new TreeSet<String>();

        // Use add() method to add elements into the Set
        set.add("Welcome");
        set.add("To");
        set.add("Geeks");
        set.add("4");
        set.add("Geeks");

        // Displaying the TreeSet
        System.out.println("TreeSet: " + set);

        // Creating an iterator
        Iterator value = set.iterator();

        // Displaying the values after iterating through the set
        System.out.println("The iterator values are: ");
        while (value.hasNext()) {
            System.out.println(value.next());
        }
    }
}
```

**输出:**

```
TreeSet: [4, Geeks, To, Welcome]
The iterator values are: 
4
Geeks
To
Welcome

```