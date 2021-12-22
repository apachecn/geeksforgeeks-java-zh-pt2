# Java 中的 TreeSet clear()方法

> 原文:[https://www.geeksforgeeks.org/treeset-clear-method-in-java/](https://www.geeksforgeeks.org/treeset-clear-method-in-java/)

Java.util.TreeSet.clear()方法用于从一个 TreeSet 中移除所有元素。使用 clear()方法只会清除集合中的所有元素，而不会删除集合。换句话说，我们可以说 clear()方法仅用于清空现有的 TreeSet。

**语法:**

```
Tree_Set.clear()
```

**参数:**该方法不取任何参数

**返回值:**函数不返回任何内容。

下面程序说明了使用 Java.util.TreeSet.clear()方法:

```
// Java code to illustrate addAll()
import java.io.*;
import java.util.TreeSet;

public class TreeSetDemo {
    public static void main(String args[])
    {
        // Creating an empty TreeSet
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

        // Clearing the TreeSet using clear() method
        tree.clear();

        // Displaying the final tree
        System.out.println("After clearing TreeSet: " + tree);
    }
}
```

**输出:**

```
TreeSet: [4, Geeks, To, TreeSet, Welcome]
After clearing TreeSet: []

```