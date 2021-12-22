# TreeSet 包含 Java 中的 All()方法，示例

> 原文:[https://www . geesforgeks . org/treeset-contains all-in-Java-method-with-example/](https://www.geeksforgeeks.org/treeset-containsall-method-in-java-with-example/)

**Java TreeSet** 的 **containsAll()** 方法用于检查两个集合是否包含相同的元素。它将一个集合作为参数，如果该集合的所有元素都存在于另一个集合中，则返回 True。

**语法:**

```java
public boolean containsAll(Collection C)
```

**参数:**参数 *C* 为集合。该参数是指需要在该集合中检查其元素出现的集合。

**返回值:**如果这个*集合*包含其他集合的所有元素，方法返回真，否则返回假。

下面的程序说明了 TreeSet.containsAll()方法:

**程序 1:**

```java
// Java code to illustrate
// TreeSet containsAll()

import java.util.*;

class TreeSetDemo {
    public static void main(String args[])
    {

        // Creating an empty set
        TreeSet<String>
            set = new TreeSet<String>();

        // Use add() method to
        // add elements in the set
        set.add("Geeks");
        set.add("for");
        set.add("Geeks");
        set.add("10");
        set.add("20");

        // prints the set
        System.out.println("TreeSet 1: "
                           + set);

        // Creating another empty set
        TreeSet<String>
            set2 = new TreeSet<String>();

        // Use add() method to
        // add elements in the set
        set2.add("Geeks");
        set2.add("for");
        set2.add("Geeks");
        set2.add("10");
        set2.add("20");

        // prints the set
        System.out.println("TreeSet 2: "
                           + set2);

        // Check if the set
        // contains same elements
        System.out.println("\nDoes set 1 contains set 2: "
                           + set.containsAll(set2));
    }
}
```

**Output:**

```java
TreeSet 1: [10, 20, Geeks, for]
TreeSet 2: [10, 20, Geeks, for]

Does set 1 contains set 2: true

```

**程序 2:**

```java
// Java code to illustrate boolean containsAll()

import java.util.*;

class TreeSetDemo {
    public static void main(String args[])
    {

        // Creating an empty set
        TreeSet<String>
            set = new TreeSet<String>();

        // Use add() method to
        // add elements in the set
        set.add("Geeks");
        set.add("for");
        set.add("Geeks");

        // prints the set
        System.out.println("TreeSet 1: "
                           + set);

        // Creating another empty set
        TreeSet<String>
            set2 = new TreeSet<String>();

        // Use add() method to
        // add elements in the set
        set2.add("10");
        set2.add("20");

        // prints the set
        System.out.println("TreeSet 2: "
                           + set2);

        // Check if the set
        // contains same elements
        System.out.println("\nDoes set 1 contains set 2: "
                           + set.containsAll(set2));
    }
}
```

**Output:**

```java
TreeSet 1: [Geeks, for]
TreeSet 2: [10, 20]

Does set 1 contains set 2: false

```