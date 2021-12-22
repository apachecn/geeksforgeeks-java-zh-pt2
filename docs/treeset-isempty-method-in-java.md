# Java 中的 TreeSet isEmpty()方法

> 原文:[https://www . geesforgeks . org/treeset-isempty-method-in-Java/](https://www.geeksforgeeks.org/treeset-isempty-method-in-java/)

Java.util.TreeSet.isEmpty()方法用于检查和验证 TreeSet 是否为空。如果树集为空，则返回真，否则返回假。

**语法:**

```
Tree_Set.isEmpty()
```

**参数:**该方法不取任何参数

**返回值:**如果集合为空，函数返回真，否则返回假。

下面程序举例说明使用 Java.util.TreeSet.isEmpty()方法:

```
// Java code to illustrate isEmpty() method
import java.util.*;
import java.util.TreeSet;

public class TreeSetDemo {
    public static void main(String args[])
    {
        // Creating an empty HashSet
        TreeSet<String> tree = new TreeSet<String>();

        // Use add() method to add elements into the Set
        tree.add("Welcome");
        tree.add("To");
        tree.add("Geeks");
        tree.add("4");
        tree.add("Geeks");
        tree.add("TreeSet");

        // Displaying the TreeSet
        System.out.println("TreeSet: " + tree);

        // Check for the empty set
        System.out.println("Is the set empty? " + tree.isEmpty());

        // Clearing the set using clear() method
        tree.clear();

        // Again Checking for the empty set
        System.out.println("Is the set empty? " + tree.isEmpty());
    }
}
```

**输出:**

```
TreeSet: [4, Geeks, To, TreeSet, Welcome]
Is the set empty? false
Is the set empty? true

```