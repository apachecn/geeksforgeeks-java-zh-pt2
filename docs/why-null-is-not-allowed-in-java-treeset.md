# 为什么 Java TreeSet 中不允许 NULL？

> 原文:[https://www . geesforgeks . org/why-null-in-Java 不允许-treeset/](https://www.geeksforgeeks.org/why-null-is-not-allowed-in-java-treeset/)

[TreeSet](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) 是 Java 中 [SortedSet 接口](https://www.geeksforgeeks.org/sortedset-java-examples/)最重要的实现之一，它使用[树](https://www.geeksforgeeks.org/binary-tree-data-structure/)进行存储。无论是否提供明确的[比较器](https://www.geeksforgeeks.org/comparator-interface-java/)，元素的顺序都由一组使用它们的自然顺序来维护。要正确实现[设置界面](https://www.geeksforgeeks.org/set-in-java/)，这必须与等号一致。

**示例:**

## Java

```
// Java Program to illustrate the TreeSet
import java.util.*;

class GFG {

    public static void main(String args[])
    {
        // Creating TreeSet and adding elements to it
        TreeSet<String> tree_set = new TreeSet<String>();

        tree_set.add("Manish");
        tree_set.add("Kartik");
        tree_set.add("Anand");
        tree_set.add("Sahil");

        // Traversing elements of TreeSet
        Iterator<String> it = tree_set.iterator();

        while (it.hasNext()) {
            System.out.println(it.next());
        }
    }
}
```

**输出**

```
Anand
Kartik
Manish
Sahil
```

**将空值添加到树集中**

在这个例子中，我们将在 TreeSet 中添加一个 NULL 值，这将给我们一个例外

## Java

```
// Adding NULL value to Java TreeSet
import java.util.TreeSet;

public class Example2 {
    public static void main(String[] args)
    {
        // Creating TreeSet and adding elements to it
        TreeSet<String> tree_Set = new TreeSet<String>();
        tree_Set.add("ABC");
        tree_Set.add(null);

        // Printing TreeSet elements
        System.out.println(tree_Set);
    }
}
```

**输出**

```
Exception in thread "main" java.lang.NullPointerException
    at java.base/java.util.TreeMap.put(TreeMap.java:561)
    at java.base/java.util.TreeSet.add(TreeSet.java:255)
    at Example2.main(Example2.java:10)
```

**说明:**默认情况下，**可比界面**由 TreeSet 内部使用，对元素进行排序。现在在可比较界面中， **compareTo()方法**用于将一个值与另一个值进行比较，以对元素进行排序。

所以因为这个目的，null 没有值，这就是为什么 compareTo()方法不能将 null 与另一个值进行比较，给出一个 **NullPointerException** 。

[添加](https://www.geeksforgeeks.org/treeset-add-method-in-java/)T3】法宣 T0】

如果我们试图在 TreeSet 中添加 **null** 值，它将在运行时生成一个 **NullPointerException** 。