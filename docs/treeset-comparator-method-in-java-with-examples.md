# Java 中的 TreeSet 比较器()方法，示例

> 原文:[https://www . geesforgeks . org/treeset-comparator-in-Java-method-with-examples/](https://www.geeksforgeeks.org/treeset-comparator-method-in-java-with-examples/)

TreeSet 是 Java 中 [SortedSet 接口](https://www.geeksforgeeks.org/sortedset-java-examples/)最重要的实现之一，它使用[树](https://www.geeksforgeeks.org/binary-tree-data-structure/)进行存储。无论是否提供明确的[比较器](https://www.geeksforgeeks.org/comparator-interface-java/)，元素的顺序都由一组使用它们的自然顺序来维护。如果要正确实现[设置界面](https://www.geeksforgeeks.org/set-in-java/)，这必须与 equals 一致。

java.util.TreeSet 中已经存在的 [*比较器()方法*](https://www.geeksforgeeks.org/comparable-vs-comparator-in-java/) 具有设置和返回比较器的重要功能，该比较器可用于对 TreeSet 中的元素进行排序。如果集合遵循元素的自然排序模式，则方法返回空值。

**语法:**

```
comp_set = (TreeSet)tree_set.comparator()
```

**参数:**该方法不取任何参数。

**返回值:**比较器集合用于以特定顺序对集合的元素进行排序。如果集合遵循默认或自然的排序模式，它将返回空值。

在这里，我们将在下面提出两个例子，前面我们将使用元素的自然排序，后面我们将使用特定的比较器来更好地理解它。

**示例 1:** 使用元素的自然排序

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate the use of comparator() method
// While using the natural ordering of the elements

// Importing utility classes
import java.util.*;

// Main class
// TreeSet Demo class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an empty TreeSet of integer type
        TreeSet<Integer> tree_set = new TreeSet<Integer>();

        // Adding elements to the set
        // using add() method
        tree_set.add(20);
        tree_set.add(24);
        tree_set.add(30);
        tree_set.add(35);
        tree_set.add(45);
        tree_set.add(50);

        // Printing elements inside TreeSet object
        System.out.println("Tree Set values are: "
                           + tree_set);

        // Creating a comparator
        Comparator comp = tree_set.comparator();

        // Print and display the comparator values
        System.out.println("Since the Comparator value is: "
                           + comp);

        // Display message only 
        System.out.println("it follows natural ordering");
    }
}
```

**Output:** 

```
Tree Set values are: [20, 24, 30, 35, 45, 50]
Since the Comparator value is: null
it follows natural ordering
```

**示例 2:** 使用特定的比较器

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate the use of comparator()
// While using a specific comparator

// Importing Comparator and TreeSet classes
// from java.util package
import java.util.Comparator;
import java.util.TreeSet;

// Class 1
// Helper class
class Helper implements Comparator<String> {

    // Method
    // To compare two strings
    public int compare(String str1, String str2)
    {

        String first_Str;
        String second_Str;

        first_Str = str1;
        second_Str = str2;

        // using compareTo() to ensure
        return second_Str.compareTo(first_Str);
    }
}

// Main class
// TreeSetDemo class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an empty TreeSet of string type
        TreeSet<String> tree_set = new TreeSet<String>();

        // Adding elements to our TreeSet object
        // using add() method
        tree_set.add("G");
        tree_set.add("E");
        tree_set.add("E");
        tree_set.add("K");
        tree_set.add("S");
        tree_set.add("4");

        // Printing elements in set before using comparator
        System.out.println("Set before using the comparator: " + tree_set);

        // Again creating an empty TreeSet of string type
        // with reference to Helper class
        TreeSet<String> tree_set1 = new TreeSet<String>(new Helper());

        // Adding elements to our TreeSet object
        // using add() method
        tree_set1.add("G");
        tree_set1.add("E");
        tree_set1.add("E");
        tree_set1.add("K");
        tree_set1.add("S");
        tree_set1.add("4");

        // Printing elements in set before using comparator
        System.out.println("The elements sorted in descending order:" + tree_set1);
    }
}
```

**Output**

```
Set before using the comparator: [4, E, G, K, S]
The elements sorted in descending order:[S, K, G, E, 4]
```