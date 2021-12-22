# Java 中的 TreeSet size()方法

> 原文:[https://www.geeksforgeeks.org/treeset-size-method-in-java/](https://www.geeksforgeeks.org/treeset-size-method-in-java/)

方法用于获取树集合的大小或树集合中存在的元素数量。

**语法:**

```java
Tree_Set.size()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回集合中元素的大小或数量。

下面程序举例说明了使用 Java.util.TreeSet.size()方法:

```java
// Java code to illustrate size()
import java.util.*;
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

        // Displaying the size of the set
        System.out.println("The size of the set is: " + tree.size());
    }
}
```

**输出:**

```java
TreeSet: [4, Geeks, To, TreeSet, Welcome]
The size of the set is: 5

```