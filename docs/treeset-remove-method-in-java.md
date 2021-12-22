# Java 中的 TreeSet remove()方法

> 原文:[https://www . geesforgeks . org/treeset-remove-method-in-Java/](https://www.geeksforgeeks.org/treeset-remove-method-in-java/)

方法是从树集中移除一个特定的元素。

**语法:**

```java
TreeSet.remove(Object O)
```

**参数:**参数 *O* 属于树集合类型，指定要从集合中移除的元素。

**返回值:**如果参数中指定的元素最初出现在集合中并成功移除，则该方法返回*真*，否则返回*假*。

下面的程序说明了 Java.util.TreeSet.remove()方法:

```java
// Java code to illustrate remove()
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

        // Removing elements using remove() method
        tree.remove("Geeks");
        tree.remove("4");
        tree.remove("TreeSet");

        // Displaying the TreeSet after removal
        System.out.println("New TreeSet: " + tree);
    }
}
```

**输出:**

```java
TreeSet: [4, Geeks, To, TreeSet, Welcome]
New TreeSet: [To, Welcome]

```