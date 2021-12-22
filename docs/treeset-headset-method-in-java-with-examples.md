# Java 中 TreeSet headSet()方法示例

> 原文:[https://www . geeksforgeeks . org/treeset-headset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/treeset-headset-method-in-java-with-examples/)

TreeSet 是 Java 中 [SortedSet 接口](https://www.geeksforgeeks.org/sortedset-java-examples/)最重要的实现之一，它使用[树](https://www.geeksforgeeks.org/binary-tree-data-structure/)进行存储。无论是否提供明确的[比较器](https://www.geeksforgeeks.org/comparator-interface-java/)，元素的顺序都由一组使用它们的自然顺序来维护。如果要正确实现[设置界面](https://www.geeksforgeeks.org/set-in-java/)，这必须与 equals 一致。

[TreeSet 类](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)的 HEADEMENT()方法已经存在于 [*java.util*](https://www.geeksforgeeks.org/java-util-package-java/) 包中，用作树集的限制设置器，以排序的方式返回方法参数中定义的限制内的元素，不包括元素。

**语法:**

```java
head_set = (TreeSet)tree_set.headSet(Object element)
```

**参数:**参数*元素*属于树集合的类型，并且是头点，该头点是除了*元素*本身之外树允许返回值的上限。

**返回值:**该方法以排序的方式返回严格小于参数中提到的元素的那部分值。

现在我们将讨论在 TreeSet 类中实现 headSet()方法时的不同场景:

*   **情况 1:** 在排序的树集中
*   **情况 2-A:** 在未排序的树集中
*   **情况 2-B:** 在未排序但具有字符串类型元素的树集中

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Illustrate headSet() method
// of TreeSet class In a sorted TreeSet

// Importing required classes
import java.io.*;
import java.util.Iterator;
import java.util.TreeSet;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an empty TreeSet by
        // declaring object of TreeSet class
        TreeSet<Integer> tree_set = new TreeSet<Integer>();

        // Adding the elements
        // using add() method
        tree_set.add(1);
        tree_set.add(2);
        tree_set.add(3);
        tree_set.add(4);
        tree_set.add(5);
        tree_set.add(10);
        tree_set.add(20);
        tree_set.add(30);
        tree_set.add(40);
        tree_set.add(50);

        // Creating the headSet tree
        TreeSet<Integer> head_set = new TreeSet<Integer>();

        // Limiting the values till 5
        head_set = (TreeSet<Integer>)tree_set.headSet(30);

        // Creating an Iterator
        Iterator iterate;
        iterate = head_set.iterator();

        // Displaying the tree set data
        System.out.println(
            "The resultant values till head set: ");

        // Holds true till there is single element
        // remaining in the object
        while (iterate.hasNext()) {

            // Iterating through the headSet
            // using next() method
            System.out.println(iterate.next() + " ");
        }
    }
}
```

**Output:** 

```java
The resultant values till head set: 
1 
2 
3 
4 
5 
10 
20
```

**例 2-A:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate headSet() method
// of TreeSet class In an unsorted TreeSet

// Importing required classes 
import java.io.*;
import java.util.Iterator;
import java.util.TreeSet;

// Main class 
public class GFG {

    // Main driver method 
    public static void main(String[] args)
    {

        // Creating an empty TreeSet
        TreeSet<Integer> tree_set = new TreeSet<Integer>();

        // Adding the elements
        // using add() method 
        tree_set.add(9);
        tree_set.add(2);
        tree_set.add(100);
        tree_set.add(40);
        tree_set.add(50);
        tree_set.add(10);
        tree_set.add(20);
        tree_set.add(30);
        tree_set.add(15);
        tree_set.add(16);

        // Creating the headSet tree
        TreeSet<Integer> head_set = new TreeSet<Integer>();

        // Limiting the values till 5
        head_set = (TreeSet<Integer>)tree_set.headSet(30);

        // Creating an Iterator
        Iterator iterate;
        iterate = head_set.iterator();

        // Displaying the tree set data
        System.out.println("The resultant values till head set: ");

        // Iterating through the headSet
        while (iterate.hasNext()) {

            // Printing the elements 
            System.out.println(iterate.next() + " ");
        }
    }
}
```

**Output:** 

```java
The resultant values till head set: 
2 
9 
10 
15 
16 
20
```

**例 2-B:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate headSet() method of TreeSet class
// In an unsorted treeset but with String type elements

// Importing required classes
import java.io.*;
import java.util.Iterator;
import java.util.TreeSet;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an empty TreeSet
        TreeSet<String> tree_set = new TreeSet<String>();

        // Adding the elements using add()
        tree_set.add("Welcome");
        tree_set.add("To");
        tree_set.add("Geek");
        tree_set.add("4");
        tree_set.add("Geeks");
        tree_set.add("TreeSet");

        // Creating the headSet tree
        TreeSet<String> head_set = new TreeSet<String>();

        // Limiting the values till 5
        head_set = (TreeSet<String>)tree_set.headSet("To");

        // Creating an Iterator
        Iterator iterate;
        iterate = head_set.iterator();

        // Displaying the tree set data
        System.out.println(
            "The resultant values till head set: ");

        // Iterating through the headSet
        while (iterate.hasNext()) {

            // Printing elements using next() method
            System.out.println(iterate.next() + " ");
        }
    }
}
```

**Output:** 

```java
The resultant values till head set: 
4 
Geek 
Geeks
```