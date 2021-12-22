# Java 中的 TreeSet tailSet()方法

> 原文:[https://www . geesforgeks . org/treeset-tailset-method-in-Java/](https://www.geeksforgeeks.org/treeset-tailset-method-in-java/)

java.util.TreeSet.tailSet()方法用于为一个树集设置一个起始点，以一种包含元素的排序方式返回所有大于作为参数传递给该方法的元素的元素(如果该元素在树中被提及)。

**语法:**

```java
*TreeSet* tail_set.tailSet(Object element)
```

**参数:**参数*元素*属于树集合的类型，是允许树返回大于包括*元素*在内的参数中提到的值的值的起点。

**返回值:**该方法以排序的方式返回值中大于参数中提到的元素的部分，包括参数。

下面的程序说明了 java.util.TreeSet.tailSet()的使用:

**程序 1:** 在排序的树集中。

```java
// Java code to illustrate TreeSet.tailSet() method
import java.io.*;
import java.util.Iterator;
import java.util.TreeSet;

public class Tree_Set_Demo {
    public static void main(String[] args)
    {

        // Creating an empty TreeSet
        TreeSet<Integer> tree_set = new TreeSet<Integer>();

        // Adding the elements using add()
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

        // Creating the tailSet tree
        TreeSet<Integer> tail_set = new TreeSet<Integer>();

        // Limiting the values till 5
        tail_set = (TreeSet<Integer>)tree_set.tailSet(10);

        // Creating an Iterator
        Iterator iterate;
        iterate = tail_set.iterator();

        // Displaying the tree set data
        System.out.println("The resultant values from the tail: ");

        // Iterating through the tailSet
        while (iterate.hasNext()) {
            System.out.println(iterate.next() + " ");
        }
    }
}
```

**Output:**

```java
The resultant values from the tail: 
10 
20 
30 
40 
50

```

**程序 2:** 在未排序的树集中。

```java
// Java code to illustrate tailSet()
import java.io.*;
import java.util.Iterator;
import java.util.TreeSet;

public class Tree_Set_Demo {
    public static void main(String[] args)
    {

        // Creating an empty TreeSet
        TreeSet<Integer> tree_set = new TreeSet<Integer>();

        // Adding the elements using add()
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

        // Creating the tailSet tree
        TreeSet<Integer> tail_set = new TreeSet<Integer>();

        // Limiting the values till 5
        tail_set = (TreeSet<Integer>)tree_set.tailSet(25);

        // Creating an Iterator
        Iterator iterate;
        iterate = tail_set.iterator();

        // Displaying the tree set data
        System.out.println("The resultant values from the tail: ");

        // Iterating through the tailSet
        while (iterate.hasNext()) {
            System.out.println(iterate.next() + " ");
        }
    }
}
```

**Output:**

```java
The resultant values from the tail: 
30 
40 
50 
100

```

**程序 3:** 在一个未排序但带有字符串类型元素的树集中。

```java
// Java code to illustrate tailSet()
import java.io.*;
import java.util.Iterator;
import java.util.TreeSet;

public class Tree_Set_Demo {
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

        // Creating the tailSet tree
        TreeSet<String> tail_set = new TreeSet<String>();

        // Limiting the values till 5
        tail_set = (TreeSet<String>)tree_set.tailSet("To");

        // Creating an Iterator
        Iterator iterate;
        iterate = tail_set.iterator();

        // Displaying the tree set data
        System.out.println("The resultant values from the tail: ");

        // Iterating through the tailSet
        while (iterate.hasNext()) {
            System.out.println(iterate.next() + " ");
        }
    }
}
```

**Output:**

```java
The resultant values from the tail: 
To 
TreeSet 
Welcome

```