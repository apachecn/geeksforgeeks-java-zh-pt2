# Java 中的 TreeSet floor()方法，带示例

> 原文:[https://www . geesforgeks . org/treeset-floor-in-Java-method-with-examples/](https://www.geeksforgeeks.org/treeset-floor-method-in-java-with-examples/)

**[Java . util . treeset<E>](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)**类的 **floor()** 方法用于返回该集合中小于或等于给定元素的最大元素，如果没有该元素，则返回 null。

**语法:**

```
public E floor(E e)
```

**参数:**该方法将值 **e** 作为待匹配的参数。

**返回值:**该方法返回小于或等于 e 的**最大元素**，如果没有该元素则返回**空值**

**异常:**如果指定元素为空，并且该集合使用自然排序，或者其比较器不允许空元素，则该方法抛出**空指针异常**

以下是举例说明**地板()**方法

**例 1:**

```
// Java program to demonstrate
// floor() method
// for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // create tree set object
            TreeSet<Integer> treeadd = new TreeSet<Integer>();

            // populate the TreeSet using add() method
            treeadd.add(10);
            treeadd.add(20);
            treeadd.add(30);
            treeadd.add(40);

            // Print the TreeSet
            System.out.println("TreeSet: " + treeadd);

            // getting the floor value for 25
            // using floor() method
            int value = treeadd.floor(25);

            // printing the floor value
            System.out.println("Floor value for 25: "
                               + value);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
TreeSet: [10, 20, 30, 40]
Floor value for 25: 20

```

**例 2:*的***为空指针异常

```
// Java program to demonstrate
// floor() method
// for NullPointerException

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {
        try {

            // create tree set object
            TreeSet<Integer> treeadd = new TreeSet<Integer>();

            // populate the TreeSet using add() method
            treeadd.add(10);
            treeadd.add(20);
            treeadd.add(30);
            treeadd.add(40);

            // Print the TreeSet
            System.out.println("TreeSet: " + treeadd);

            // getting the floor value for null
            // using floor() method
            System.out.println("Trying to get"
                               + " the floor value"
                               + " for null");

            int value = treeadd.floor(null);

            // printing the floor value
            System.out.println("Floor value for 25: "
                               + value);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
TreeSet: [10, 20, 30, 40]
Trying to get the floor value for null
Exception thrown : java.lang.NullPointerException

```