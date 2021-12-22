# Java 中的 SortedSet removeAll()方法，带示例

> 原文:[https://www . geesforgeks . org/sorted set-remove all-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedset-removeall-method-in-java-with-examples/)

**[SortedSet](https://www.geeksforgeeks.org/sortedset-java-examples/)** 接口的 **removeAll()** 方法用于从此 SortedSet 中移除指定集合中包含的所有元素。

**语法:**

```java
public boolean removeAll(Collection c)
```

**参数:**该方法将**集合 c** 作为包含要从该排序集中移除的元素的参数。

**返回值:**如果该设置因调用而改变，则该方法返回**真**。

**异常:**如果该集合包含空元素，并且指定的集合不允许空元素(可选)，或者指定的集合为空，则该方法抛出**空指针异常**。

**注**:[sorted Set](https://www.geeksforgeeks.org/sortedset-java-examples/)中的 removeAll()方法继承了 Java 中的 [Set 接口](https://www.geeksforgeeks.org/set-in-java/)。

以下是说明 *removeAll()* 方法的示例。

**例 1:**

```java
// Java program to demonstrate
// removeAll() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] args)
        throws Exception
    {

        try {
            // Creating object of SortedSet
            SortedSet<Integer> set1
                = new TreeSet<Integer>();

            // Populating set1
            set1.add(1);
            set1.add(2);
            set1.add(3);
            set1.add(4);
            set1.add(5);

            // print set1
            System.out.println(
                "Set before "
                + "removeAll() operation : "
                + set1);

            // Creating another object of Set
            SortedSet<Integer> set2
                = new TreeSet<Integer>();
            set2.add(1);
            set2.add(2);
            set2.add(3);

            // print set2
            System.out.println(
                "Collection Elements "
                + "to be removed : "
                + set2);

            // Removing elemnts from set
            // specified in set2
            // using removeAll() method
            set1.removeAll(set2);

            // print set1
            System.out.println(
                "Set after "
                + "removeAll() operation : "
                + set1);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : "
                               + e);
        }
    }
}
```

**输出:**

```java
Set before removeAll() operation : [1, 2, 3, 4, 5]
Collection Elements to be removed : [1, 2, 3]
Set after removeAll() operation : [4, 5]

```

**例 2:** 为*零点异常*。

```java
// Java program to demonstrate
// removeAll() method for Integer value

import java.util.*;

public class GFG1 {

    public static void main(String[] args)
        throws Exception
    {
        try {

            // Creating object of SortedSet
            SortedSet<Integer> set1
                = new TreeSet<Integer>();

            // Populating set1
            set1.add(1);
            set1.add(2);
            set1.add(3);
            set1.add(4);
            set1.add(5);

            // print set1
            System.out.println(
                "Set before "
                + "removeAll() operation : "
                + set1);

            // Creating another object of SortedSet<Integer>
            SortedSet<Integer> set2 = null;

            // print set2
            System.out.println(
                "Collection Elements"
                + " to be removed : "
                + set2);

            System.out.println(
                "\nTrying to pass "
                + "null as a specified element\n");

            // Removing elemnts from set
            // specified in set2
            // using removeAll() method
            set1.removeAll(set2);

            // print set1
            System.out.println(
                "Set after "
                + "removeAll() operation : "
                + set1);
        }

        catch (NullPointerException e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
Set before removeAll() operation : [1, 2, 3, 4, 5]
Collection Elements to be removed : null

Trying to pass null as a specified element

java.lang.NullPointerException

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/set . html # removeAll(Java . util . collection)](https://docs.oracle.com/javase/7/docs/api/java/util/Set.html#removeAll(java.util.Collection))