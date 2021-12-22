# Java 中的 TreeSet higher()方法，示例

> 原文:[https://www . geesforgeks . org/treeset-higher-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/treeset-higher-method-in-java-with-examples/)

Java 中 TreeSet 类的 **higher(E ele)** 方法用于返回该集合中最少的元素，该元素严格大于给定的元素 *ele* 。如果没有这样的元素，那么这个方法返回空值。

这里，E 是这个 TreeSet 集合维护的元素类型。

**语法**:

```java
public E higher(E ele)
```

**参数:**只需要一个参数 **ele** 。它是确定集合中严格大于该值的最小值所基于的元素。

**返回值:**它返回该树集合存储的类型的值，该值为空或所需值。

**异常:**

*   **ClassCastException** :如果指定的元素不能与集合的元素进行比较，这个方法抛出一个 ClassCastException。
*   **NullPointerException** :如果给定的元素为空，并且集合使用自然排序或者比较器不允许空值，那么这个方法抛出一个 NullPointerException。

以下程序说明了上述方法:
**程序 1** :

```java
// Java program to illustrate the
// TreeSet higher() method

import java.util.TreeSet;
public class GFG {
    public static void main(String args[])
    {
        TreeSet<Integer> tree = new TreeSet<Integer>();
        tree.add(10);
        tree.add(5);
        tree.add(8);
        tree.add(1);
        tree.add(11);
        tree.add(3);

        System.out.println(tree.higher(10));
    }
}
```

**Output:**

```java
11

```

**程序 2:**

```java
// Java program to illustrate the
// TreeSet higher() method

import java.util.TreeSet;
public class GFG {
    public static void main(String args[])
    {
        TreeSet<Integer> tree = new TreeSet<Integer>();

        tree.add(10);
        tree.add(5);
        tree.add(8);
        tree.add(1);
        tree.add(11);
        tree.add(3);

        System.out.println(tree.higher(15));
    }
}
```

**Output:**

```java
null

```

**程序 3** :演示空指针异常的程序。

```java
// Java program to illustrate the
// TreeSet higher() method

import java.util.TreeSet;
public class GFG {
    public static void main(String args[])
    {
        TreeSet<String> tree = new TreeSet<String>();

        tree.add("10");
        tree.add("5");
        tree.add("8");
        tree.add("1");
        tree.add("11");
        tree.add("3");

        // Pass a NULL to the method
        try {
            System.out.println(tree.higher(null));
        } // Catch the Exception
        catch (Exception e) {

            // Print the Exception
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
java.lang.NullPointerException

```

**程序 4** :演示 ClassCastException。

```java
// Java program to illustrate the
// TreeSet higher() method

import java.util.ArrayList;
import java.util.LinkedList;
import java.util.List;
import java.util.TreeSet;

public class GFG {
    public static void main(String args[])
    {
        TreeSet<List> tree = new TreeSet<List>();
        List<Integer> l1 = new LinkedList<Integer>();

        try {

            l1.add(1);
            l1.add(2);
            tree.add(l1);

            List<Integer> l2 = new LinkedList<Integer>();
            l2.add(3);
            l2.add(4);

            List<Integer> l3 = new ArrayList<Integer>();
            l2.add(5);
            l2.add(6);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
java.lang.ClassCastException: java.util.LinkedList cannot be cast to java.lang.Comparable

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/treeset . html # high(E)](https://docs.oracle.com/javase/7/docs/api/java/util/TreeSet.html#higher(E))