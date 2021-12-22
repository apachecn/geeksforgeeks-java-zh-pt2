# Java 中的 TreeSet last()方法

> 原文:[https://www.geeksforgeeks.org/treeset-last-method-in-java/](https://www.geeksforgeeks.org/treeset-last-method-in-java/)

Java.util.TreeSet.last()方法用于返回 TreeSet 元素的最后一个元素。这里的最后一个元素是指集合中最高的元素。如果元素是整数类型，则返回最大的整数。如果元素是字符串类型，那么元素将按字母顺序进行检查，并且以字典顺序中最后一个字母开始的字符串将被返回，而与长度无关。

**语法:**

```
Tree_Set.last()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回集合中最高的成员。如果元素是字符串类型，则不管长度如何，都按字母顺序进行检查；如果元素是整数类型，则返回最大的整数。字母表类型的字符串被赋予更高的优先级。

下面是说明使用 Java.util.TreeSet.last()方法的程序:
**程序 1:** 当元素是整数类型时:

```
// Java code to illustrate last()
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

        // Displaying the highest element of the set
        System.out.println("The last element is: " + tree.last());
    }
}
```

**Output:**

```
TreeSet: [7, 8, 14, 48, 124, 200]
The last element is: 200

```

**程序 2:** 当元素是字符串类型时:

```
// Java code to illustrate last()
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

        // Displaying the highest element of the set
        System.out.println("The last element is: " + tree.last());
    }
}
```

**Output:**

```
TreeSet: [Ab, B, Geeks, To, TreeSet, Welcome]
The last element is: Welcome

```

**程序 3:** 当元素为字符串类型但带有整数值时。这里我们看到字典中出现在最后的字母被赋予了更高的优先级:

```
// Java code to illustrate last()
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
        tree.add("90000000");
        tree.add("Z");

        // Displaying the TreeSet
        System.out.println("TreeSet: " + tree);

        // Displaying the highest element of the set
        System.out.println("The last element is: " + tree.last());
    }
}
```

**Output:**

```
TreeSet: [45, 90000000, Geeks, To, Welcome, Z]
The last element is: Z

```