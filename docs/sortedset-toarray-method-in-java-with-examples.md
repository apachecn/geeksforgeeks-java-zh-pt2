# 用示例排序 Java 中的 toArray()方法

> 原文:[https://www . geesforgeks . org/sorted set-to array-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedset-toarray-method-in-java-with-examples/)

**[Java SortedSet](https://www.geeksforgeeks.org/sortedset-java-examples/)** 的 **toArray()** 方法用于形成与 SortedSet 相同元素的数组。基本上，它将 SortedSet 中的所有元素复制到一个新数组中。

**语法:**

```
Object[] toArray()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个包含类似于排序集的元素的**数组**。

**注**:[sorted Set](https://www.geeksforgeeks.org/sortedset-java-examples/)中的 toArray()方法继承了 Java 中的 [Set 接口](https://www.geeksforgeeks.org/set-in-java/)。

下面的程序说明了 SortedSet.toArray()方法:

**程序 1:**

```
// Java code to illustrate toArray()

import java.util.*;

public class SortedSetDemo {
    public static void main(String args[])
    {

        // Creating an empty SortedSet
        SortedSet<String> abs_col
            = new TreeSet<String>();

        // Use add() method to add
        // elements into the SortedSet
        abs_col.add("Welcome");
        abs_col.add("To");
        abs_col.add("Geeks");
        abs_col.add("For");
        abs_col.add("Geeks");

        // Displaying the Set
        System.out.println("The SortedSet: "
                           + abs_col);

        // Creating the array and using toArray()
        Object[] arr = abs_col.toArray();

        System.out.println("The array is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**输出:**

```
The SortedSet: [For, Geeks, To, Welcome]
The array is:
For
Geeks
To
Welcome

```

**程序二:**

```
// Java code to illustrate toArray()

import java.util.*;

public class SetDemo {
    public static void main(String args[])
    {
        // Creating an empty SortedSet
        SortedSet<Integer> abs_col
            = new TreeSet<Integer>();

        // Use add() method to add
        // elements into the SortedSet
        abs_col.add(10);
        abs_col.add(15);
        abs_col.add(30);
        abs_col.add(20);
        abs_col.add(5);
        abs_col.add(25);

        // Displaying the SortedSet
        System.out.println("The SortedSet: "
                           + abs_col);

        // Creating the array and using toArray()
        Object[] arr = abs_col.toArray();

        System.out.println("The array is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**输出:**

```
The SortedSet: [5, 10, 15, 20, 25, 30]
The array is:
5
10
15
20
25
30

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/set . html # to array()](https://docs.oracle.com/javase/7/docs/api/java/util/Set.html#toArray())