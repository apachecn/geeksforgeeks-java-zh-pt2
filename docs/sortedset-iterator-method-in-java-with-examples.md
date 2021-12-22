# Java 中的 SortedSet 迭代器()方法，带示例

> 原文:[https://www . geesforgeks . org/sorted set-iterator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedset-iterator-method-in-java-with-examples/)

**[java.util.SortedSet](https://www.geeksforgeeks.org/sortedset-java-examples/) 。iterator()** 方法用于返回与集合元素相同的迭代器。元素从集合中随机返回。

**语法:**

```
Iterator *iterate_value* = *sortedSetInstance*.iterator();

```

**参数:**函数不取任何参数。

**返回值:**方法迭代集合的元素并返回值(迭代器)。

**注**:[sorted Set](https://www.geeksforgeeks.org/sortedset-java-examples/)中的迭代器()方法继承了 Java 中的 [Set 接口](https://www.geeksforgeeks.org/set-in-java/)。

下面程序举例说明了 java.util.Set.iterator()方法:

```
// Java code to illustrate iterator()

import java.util.*;

public class SortedSetDemo {
    public static void main(String args[])
    {

        // Creating an empty Set
        SortedSet<String> set
            = new TreeSet<String>();

        // Use add() method to
        // add elements into the Set
        set.add("Welcome");
        set.add("To");
        set.add("Geeks");
        set.add("4");
        set.add("Geeks");

        // Displaying the Set
        System.out.println("SortedSet: "
                           + set);

        // Creating an iterator
        Iterator value = set.iterator();

        // Displaying the values after
        // iterating through the iterator
        System.out.println("The iterator values are: ");
        while (value.hasNext()) {
            System.out.println(value.next());
        }
    }
}
```

**输出:**

```
SortedSet: [4, Geeks, To, Welcome]
The iterator values are: 
4
Geeks
To
Welcome

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/set . html # iterator()](https://docs.oracle.com/javase/7/docs/api/java/util/Set.html#iterator())