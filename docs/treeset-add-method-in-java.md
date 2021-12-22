# Java 中的 TreeSet add()方法

> 原文:[https://www.geeksforgeeks.org/treeset-add-method-in-java/](https://www.geeksforgeeks.org/treeset-add-method-in-java/)

Java TreeSet 中的 Java.util.TreeSet.add()方法用于将特定元素添加到 TreeSet 中。只有当集合中不存在指定的元素时，函数才会添加元素，否则，如果元素不存在于树集合中，函数将返回 False。

**语法:**

```java
Tree_Set.add(Object element)
```

**参数:**参数*元素*属于树集类型，是指要添加到树集中的元素。

**返回值:**如果元素不在集合中并且是新的，函数返回真，否则如果元素已经在集合中，函数返回假。

下面程序说明了使用 Java.util.TreeSet.add()方法:

```java
// Java code to illustrate add()
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
    }
}
```

**输出:**

```java
TreeSet: [4, Geeks, To, TreeSet, Welcome]

```