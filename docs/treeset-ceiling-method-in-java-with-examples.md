# Java 中 TreeSet 天花板()方法，示例

> 原文:[https://www . geesforgeks . org/treeset-天花板-java 中的方法-示例/](https://www.geeksforgeeks.org/treeset-ceiling-method-in-java-with-examples/)

**[Java . util . treeset<E>](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)**类的**天花板()**方法用于返回该集合中大于或等于给定元素的最少元素，如果没有该元素，则返回 null。

**语法:**

```java
public E ceiling(E e)
```

**参数:**该方法将值 **e** 作为待匹配的参数。

**返回值:**该方法返回大于等于 e 的**最小元素**，如果没有则返回**空值**。

**异常:**如果指定的元素为空，并且该集合使用自然排序，或者其比较器不允许空元素，则该方法抛出**空指针异常**。

以下是举例说明*上限()*方法

**例 1:**

```java
// Java program to demonstrate
// ceiling() method

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // create tree set object
            TreeSet<Integer> treeadd = new TreeSet<Integer>();

            // populate the TreeSet
            treeadd.add(10);
            treeadd.add(20);
            treeadd.add(30);
            treeadd.add(40);

            // Print the TreeSet
            System.out.println("TreeSet: " + treeadd);

            // getting ceiling value for 25
            // using ceiling() method
            int value = treeadd.ceiling(25);

            // printing  the ceiling value
            System.out.println("Ceiling value for 25: "
                               + value);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
TreeSet: [10, 20, 30, 40]
Ceiling value for 25: 30

```

**示例 2:** 演示*空指针异常*。

```java
// Java program to demonstrate
// ceiling() method for NullPointerException

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // create tree set object
            TreeSet<Integer> treeadd = new TreeSet<Integer>();

            // populate the TreeSet
            treeadd.add(10);
            treeadd.add(20);
            treeadd.add(30);
            treeadd.add(40);

            // Print the TreeSet
            System.out.println("TreeSet: " + treeadd);

            // getting ceiling value for null
            // using ceiling() method
            System.out.println("Trying to compare"
                               + " with null value ");

            int value = treeadd.ceiling(null);

            // printing  the ceiling value
            System.out.println("Ceiling value for null: " + value);
        }

        catch (NullPointerException e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
TreeSet: [10, 20, 30, 40]
Trying to compare with null value 
Exception: java.lang.NullPointerException

```