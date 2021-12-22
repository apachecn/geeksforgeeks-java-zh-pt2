# 遍历 Java 中的 HashSet

> 原文:[https://www . geesforgeks . org/traverse-through-a-hashset-in-Java/](https://www.geeksforgeeks.org/traverse-through-a-hashset-in-java/)

众所周知 [**HashSet**](https://www.geeksforgeeks.org/hashset-in-java/) 元素是无序的，所以遍历的元素可以任意顺序打印。为了在我们的 HashSet 上执行操作，比如插入、删除、更新元素，我们首先需要伸出手来访问 HashSet。下面是一些我们可以迭代元素来执行如下所列的集合元素的操作的方法。

**方法:**

1.  使用 for-each 循环
2.  使用 forEach 方法
3.  使用迭代器

**方法 1:** [每个循环使用](https://www.geeksforgeeks.org/for-each-loop-in-java/)

这是 Java 5 中引入的另一种类似 for 循环、while 循环、do-while 循环的数组遍历技术。它以的关键字**开始，就像普通的 for 循环一样。您不是声明和初始化循环计数器变量，而是声明一个与数组的基类型相同的变量，后跟一个冒号，然后是数组名数组遍历技术，如 Java 5 中引入的 for 循环、while 循环、do-while 循环。**

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate iteration over
// HashSet using an Enhanced for-loop

import java.util.*;

class IterationDemo {
    public static void main(String[] args)
    {
        // your code goes here
        HashSet<String> h = new HashSet<String>();

        // Adding elements into HashSet using add()
        h.add("Geeks");
        h.add("for");
        h.add("Geeks");

        // Iterating over hash set items
        for (String i : h) 
            System.out.println(i);        
    }
}
```

**Output**

```java
Geeks
for
```

**方法 2:** [使用 Stream 类的 forEach()方法](https://www.geeksforgeeks.org/stream-foreach-method-java-examples/)

**流 forEach(消费者动作)**为流的每个元素执行一个动作。Stream forEach(消费者行动)是一种 ***终端操作*** 也就是说，它可能会穿越该流以产生结果或副作用。

> **提示:**在 Java 8 或更高版本中，我们可以使用 *forEach()* 方法迭代一个 List 或 Collection。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate iteration over
// HashSet using forEach() method

import java.util.*;

class IterationDemo {
    public static void main(String[] args)
    {
        // your code goes here
        HashSet<String> h = new HashSet<String>();

        // Adding elements into HashSet using add()
        h.add("Geeks");
        h.add("for");
        h.add("Geeks");

        // Iterating over hash set items
        h.forEach(i -> System.out.println(i));
    }
}
```

**Output:** 

```java
Geeks
for
```

**方法 3:** [使用迭代器](https://www.geeksforgeeks.org/iterators-in-java/)

iterator()方法用于获取该集合中元素的迭代器。元素没有特定的返回顺序。下面是演示它的 java 程序。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Illustrate Traversal over HashSet
// Using an iterator

// Importing required classes
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating empty HashSet by declaring object
        // of HashSet class of string type
        HashSet<String> h = new HashSet<String>();

        // Adding elements into HashSet
        // using add() method
        h.add("Geeks");
        h.add("for");
        h.add("Geeks");

        // Iterating over HashSet elements
        // using iterator
        Iterator<String> i = h.iterator();

        // Holds true till there is single element remaining
        // in the Set
        while (i.hasNext())

            // Printing the elements
            System.out.println(i.next());
    }
}
```

**Output**

```java
Geeks
for
```