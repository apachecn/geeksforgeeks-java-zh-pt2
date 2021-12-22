# Java 中的 SortedSet retainAll()方法，带示例

> 原文:[https://www . geesforgeks . org/sorted set-retain all-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedset-retainall-method-in-java-with-examples/)

[](https://www.geeksforgeeks.org/sortedset-java-examples/)**接口的 **retainAll()** 方法用于从这个 SortedSet 中保留指定集合中包含的所有元素。**

****语法:****

```
public boolean retainAll(Collection c)
```

****参数:**该方法将**集合 c** 作为一个包含要从该排序集中保留的元素的参数。**

****返回值:**如果这个排序集由于调用而改变，这个方法返回**真**。**

****异常:**如果该集合包含空元素，并且指定的集合不允许空元素(可选)，或者指定的集合为空，则该方法抛出**空指针异常**。**

****注**:[sorted Set](https://www.geeksforgeeks.org/sortedset-java-examples/)中的 retainAll()方法继承了 Java 中的 [Set 接口](https://www.geeksforgeeks.org/set-in-java/)。**

**以下是说明*retainal()*方法的例子。**

****例 1:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to demonstrate
// retainAll() method for Sorted set

import java.util.*;

public class GFG1 {
    public static void main(String[] args)
        throws Exception
    {

        try {

            // Creating object of Set
            SortedSet<Integer> arrset1
                = new TreeSet<Integer>();

            // Populating arrset1
            arrset1.add(1);
            arrset1.add(2);
            arrset1.add(3);
            arrset1.add(4);
            arrset1.add(5);

            // print arrset1
            System.out.println(
                "Set before "
                + "retainAll() operation : "
                + arrset1);

            // Creating another object of  Set
            SortedSet<Integer> arrset2
                = new TreeSet<Integer>();
            arrset2.add(1);
            arrset2.add(2);
            arrset2.add(3);

            // print arrset2
            System.out.println(
                "Collection Elements"
                + " to be retained : "
                + arrset2);

            // Removing elements from arrset
            // specified in arrset2
            // using retainAll() method
            arrset1.retainAll(arrset2);

            // print arrset1
            System.out.println(
                "Set after "
                + "retainAll() operation : "
                + arrset1);
        }

        catch (NullPointerException e) {
            System.out.println(e);
        }
    }
}
```

****Output:** 

```
Set before retainAll() operation : [1, 2, 3, 4, 5]
Collection Elements to be retained : [1, 2, 3]
Set after retainAll() operation : [1, 2, 3]
```** 

****例 2:** 为*零点异常*。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to demonstrate
// retainAll() method for Sorted set

import java.util.*;

public class GFG1 {
    public static void main(String[] args)
        throws Exception
    {
        try {

            // Creating object of SortedSet<Integer>
            SortedSet<Integer> arrset1
                = new TreeSet<Integer>();

            // Populating arrset1
            arrset1.add(1);
            arrset1.add(2);
            arrset1.add(3);
            arrset1.add(4);
            arrset1.add(5);

            // print arrset1
            System.out.println(
                "Set before "
                + "retainAll() operation : "
                + arrset1);

            // Creating another object of Set<Integer>
            SortedSet<Integer> arrset2 = null;

            // print arrset2
            System.out.println(
                "Collection Elements "
                + "to be retained : "
                + arrset2);

            System.out.println(
                "\nTrying to pass "
                + "null as a "
                + "specified element\n");

            // Removing elements from arrset
            // specified in arrset2
            // using retainAll() method
            arrset1.retainAll(arrset2);

            // print arrset1
            System.out.println(
                "Set after "
                + "retainAll() operation : "
                + arrset1);
        }

        catch (NullPointerException e) {
            System.out.println(e);
        }
    }
}
```

****Output:** 

```
Set before retainAll() operation : [1, 2, 3, 4, 5]
Collection Elements to be retained : null

Trying to pass null as a specified element

java.lang.NullPointerException
```** 

****参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/set . html # retailnall(Java . util . collection)](https://docs.oracle.com/javase/7/docs/api/java/util/Set.html#retainAll(java.util.Collection))T4】**