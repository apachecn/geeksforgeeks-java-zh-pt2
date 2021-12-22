# Java 中的 TreeSet 克隆()方法

> 原文:[https://www.geeksforgeeks.org/treeset-clone-method-in-java/](https://www.geeksforgeeks.org/treeset-clone-method-in-java/)

Java.util.TreeSet.clone()方法用于返回上述树集的浅拷贝。它只是创建了一个集合的副本。

**语法:**

```
Tree_Set.clone()
```

**参数:**该方法不取任何参数。

**返回值:**函数只返回一个 TreeSet 的副本。

下面程序举例说明了使用 Java.util.TreeSet.clone()方法:

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

        // Creating a new cloned set
        TreeSet cloned_set = new TreeSet();

        // Cloning the set using clone() method
        cloned_set = (TreeSet)tree.clone();

        // Displaying the cloned_set
        System.out.println("The cloned TreeSet: " + cloned_set);
    }
}
```

**输出:**

```
TreeSet: [4, Geeks, To, TreeSet, Welcome]
The cloned TreeSet: [4, Geeks, To, TreeSet, Welcome]

```