# Java 中的 TreeSet addAll()方法

> 原文:[https://www . geesforgeks . org/treeset-addall-method-in-Java/](https://www.geeksforgeeks.org/treeset-addall-method-in-java/)

**Java . util . treeset . addall(Collection C)**方法用于将上述集合中的所有元素追加到现有集合中。元素是随机添加的，没有任何特定的顺序。
**语法:**

```
boolean addAll(Collection C)
```

**参数:**参数 *C* 是要添加到树集中的任何类型的集合。

**返回值:**如果该方法成功地将集合 *C* 的元素追加到树集中，则该方法返回真，否则返回假。

下面的程序说明了 Java.util.TreeSet.addAll()方法:
**程序 1 :** 追加一个树集。

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

        // Creating anothe TreeSet
        TreeSet<String> tree_two = new TreeSet<String>();

        // Use add() method to add elements into the Set
        tree_two.add("Hello");
        tree_two.add("World");

        // Using addAll() method to Append
        tree.addAll(tree_two);

        // Displaying the final tree
        System.out.println("TreeSet: " + tree);
    }
}
```

**Output:**

```
TreeSet: [4, Geeks, To, TreeSet, Welcome]
TreeSet: [4, Geeks, Hello, To, TreeSet, Welcome, World]

```

**程序 2 :** 追加数组列表。

```
// Java code to illustrate addAll()
import java.io.*;
import java.util.TreeSet;
import java.util.ArrayList;

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

        // An array collection is created
        ArrayList<String> collect = new ArrayList<String>();
        collect.add("A");
        collect.add("Computer");
        collect.add("Portal");

        // Using addAll() method to Append
        tree.addAll(collect);

        // Displaying the final tree
        System.out.println("Final TreeSet: " + tree);
    }
}
```

**Output:**

```
TreeSet: [4, Geeks, To, TreeSet, Welcome]
Final TreeSet: [4, A, Computer, Geeks, Portal, To, TreeSet, Welcome]

```