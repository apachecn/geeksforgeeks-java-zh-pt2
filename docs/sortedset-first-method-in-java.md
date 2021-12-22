# Java 中的 SortedSet first()方法

> 原文:[https://www . geesforgeks . org/sorted set-Java 中的第一种方法/](https://www.geeksforgeeks.org/sortedset-first-method-in-java/)

Java 中 [SortedSet 接口的第一个()方法用于返回第一个，即当前在这个集合中最低的元素。
**语法** :](https://www.geeksforgeeks.org/sortedset-java-examples/) 

```
E first()
```

其中，E 是该集合维护的元素类型。
**参数**:本功能不接受任何参数。
**返回值**:返回集合中当前第一个或最低的元素。
**异常**:如果集合为空，则抛出 **NoSuchElementException** 。
以下程序举例说明上述方法:
**程序 1** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// A Java program to demonstrate
// working of SortedSet

import java.util.SortedSet;
import java.util.TreeSet;

public class Main {
    public static void main(String[] args)
    {
        // Create a TreeSet and inserting elements
        SortedSet<Integer> s = new TreeSet<>();

        // Adding Element to SortedSet
        s.add(1);
        s.add(5);
        s.add(2);
        s.add(3);
        s.add(9);

        // Returning the lowest element from set
        System.out.print("Lowest element in set is : "
                         + s.first());
    }
}
```

**Output:** 

```
Lowest element in set is : 1
```

**节目 2** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Program to illustrate the first()
// method of SortedSet interface

import java.util.SortedSet;
import java.util.TreeSet;

public class GFG {
    public static void main(String args[])
    {
        // Create an empty SortedSet
        SortedSet<Integer> s = new TreeSet<>();

        // Trying to access element from
        // empty set
        try {
            s.first();
        }
        catch (Exception e) {
            // throws NoSuchElementException
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:** 

```
Exception: java.util.NoSuchElementException
```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/util/sorted set . html # first()](https://docs.oracle.com/javase/10/docs/api/java/util/SortedSet.html#first())