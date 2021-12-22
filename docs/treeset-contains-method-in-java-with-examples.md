# TreeSet 包含 Java 中的()方法，示例

> 原文:[https://www . geesforgeks . org/treeset-contains-method-in-Java-with-examples/](https://www.geeksforgeeks.org/treeset-contains-method-in-java-with-examples/)

TreeSet 是 Java 中 [SortedSet 接口](https://www.geeksforgeeks.org/sortedset-java-examples/)最重要的实现之一，它使用[树](https://www.geeksforgeeks.org/binary-tree-data-structure/)进行存储。无论是否提供明确的[比较器](https://www.geeksforgeeks.org/comparator-interface-java/)，元素的顺序都由一组使用它们的自然顺序来维护。如果要正确实现[设置界面](https://www.geeksforgeeks.org/set-in-java/)，这必须与 equals 一致。

这个类提供了很多方法，让我们来讨论一下 ***包含的是 [TreeSet 类](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)的()方法*** 存在于 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中，用于检查 TreeSet 中是否存在特定的元素。所以基本上它是用来检查一个 TreeSet 是否包含任何特定的元素。

**语法:**

```java
Tree_Set.contains(Object element)
```

**参数:**树集的类型。这是需要检查它是否存在于树集中的元素。

**返回值:**一个布尔值，如果元素存在于集合中则为真，否则返回假。

**异常:**它抛出如下所列的两种类型的异常:

*   [【null 指针异常:](https://www.geeksforgeeks.org/null-pointer-exception-in-java/) **喂！喂！喂空值**
*   **[ClasscasteException:](https://www.geeksforgeeks.org/how-to-fix-java-lang-classcastexception-in-java/) If the specified element cannot be compared with the element currently existing in the collection.**

 **> **提示:**正如我们所知，treeSet 使用自然排序，其比较器不允许空元素，因此出现了空指针异常。

**示例**

## Java

```java
// Java Program to Illustrate contains() method
// of TreeSet class

// Importing required classes
import java.io.*;
import java.util.TreeSet;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Creating an empty TreeSet of string type
        TreeSet<String> tree = new TreeSet<String>();

        // Adding elements in TreeSet
        // Using add() method to
        tree.add("Welcome");
        tree.add("To");
        tree.add("Geeks");
        tree.add("4");
        tree.add("Geeks");
        tree.add("TreeSet");

        // Displaying the TreeSet
        System.out.println("TreeSet: " + tree);

        // Use-case 1
        // Check for specific element in the above TreeSet
        // object using contains() method of TreeSet class

        // Printing a boolean value
        System.out.println(
            "Does the Set contains 'TreeSet'? "
            + tree.contains("TreeSet"));

        // Use-case 2
        // Check for specific element in the above TreeSet
        // object Say custom elelemnt be "4"
        System.out.println("Does the Set contains '4'? "
                           + tree.contains("4"));

        // Use-case 3
        // Check if the list contains "No"
        System.out.println("Does the Set contains 'No'? "
                           + tree.contains("No"));
    }
}
```

**输出:**

```java
TreeSet: [4, Geeks, To, TreeSet, Welcome]
Does the Set contains 'TreeSet'? true
Does the Set contains '4'? true
Does the Set contains 'No'? false
```

**输出说明:**

当我们在 TreeSet***{“欢迎”、“到”、“极客”、“4”、“极客”、“TreeSet”}***中插入元素时，我们检查特定元素，绕过元素作为 contains()方法的参数，如果存在，返回布尔值 true，否则返回布尔值 false。要记住的关键点是，在 java 中，我们只有布尔值的真-假，也没有 0-1，请极客们注意。**