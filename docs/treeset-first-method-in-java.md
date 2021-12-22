# Java 中的 TreeSet first()方法

> 原文:[https://www.geeksforgeeks.org/treeset-first-method-in-java/](https://www.geeksforgeeks.org/treeset-first-method-in-java/)

Java.util.TreeSet.first()方法用于返回 TreeSet 元素的第一个元素。这里的**第一个元素**是指集合中最低的元素。如果元素是整数类型，则返回最小的整数。如果元素是字符串类型，那么元素将按字母顺序进行检查，并且以字典顺序中的初始字母开始的字符串将被返回，而与长度无关。

**语法:**

```java
Tree_Set.first()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回集合中最低的成员。如果元素是字符串类型，则不管长度如何，都按字母顺序进行检查；如果元素是整数类型，则返回最小的整数。此外，字符串类型的数字具有更高的优先级。

下面是说明使用 Java.util.TreeSet.first()方法的程序:
**程序 1:** 当元素是整数类型时。

```java
// Java code to illustrate first()
import java.util.*;
import java.util.TreeSet;

public class TreeSetDemo {
    public static void main(String args[])
    {
        // Creating an empty TreeSet
        TreeSet<Integer> tree = new TreeSet<Integer>();

        // Use add() method to add elements into the Set
        tree.add(14);
        tree.add(8);
        tree.add(200);
        tree.add(48);
        tree.add(7);
        tree.add(124);

        // Displaying the TreeSet
        System.out.println("TreeSet: " + tree);

        // Displaying the lowest element of the set
        System.out.println("The first element is: " + tree.first());
    }
}
```

**Output:**

```java
TreeSet: [7, 8, 14, 48, 124, 200]
The first element is: 7

```

**程序 2:** 当元素为字符串类型时。

```java
// Java code to illustrate first()
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
        tree.add("Ab");
        tree.add("TreeSet");
        tree.add("B");

        // Displaying the TreeSet
        System.out.println("TreeSet: " + tree);

        // Displaying the lowest element of the set
        System.out.println("The first element is: " + tree.first());
    }
}
```

**Output:**

```java
TreeSet: [Ab, B, Geeks, To, TreeSet, Welcome]
The first element is: Ab

```

**程序 3:** 当元素为字符串类型但带有整数值时。这里我们看到首先出现的数字被认为是第一个元素，与长度无关:

```java
// Java code to illustrate first()
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
        tree.add("45");
        tree.add("100");
        tree.add("5");

        // Displaying the TreeSet
        System.out.println("TreeSet: " + tree);

        // Displaying the lowest element of the set
        System.out.println("The first element is: " + tree.first());
    }
}
```

**Output:**

```java
TreeSet: [100, 45, 5, Geeks, To, Welcome]
The first element is: 100

```