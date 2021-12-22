# Java 中的 TreeSet toArray()方法，示例

> 原文:[https://www . geesforgeks . org/treeset-to array-method-in-Java-with-example/](https://www.geeksforgeeks.org/treeset-toarray-method-in-java-with-example/)

**Java TreeSet** 的 **toArray()** 方法用于形成与 TreeSet 相同元素的数组。基本上，它将一个 TreeSet 中的所有元素复制到一个新的数组中。

**语法:**

```
Object[] arr = TreeSet.toArray()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个包含类似于 TreeSet 元素的数组。

下面的程序说明了 TreeSet.toArray()方法:

**程序 1:**

```
// Java code to illustrate toArray()

import java.util.*;

public class TreeSetDemo {
    public static void main(String args[])
    {
        // Creating an empty TreeSet
        TreeSet<String>
            set = new TreeSet<String>();

        // Use add() method to add
        // elements into the TreeSet
        set.add("Welcome");
        set.add("To");
        set.add("Geeks");
        set.add("For");
        set.add("Geeks");

        // Displaying the TreeSet
        System.out.println("The TreeSet: "
                           + set);

        // Creating the array and using toArray()
        Object[] arr = set.toArray();

        System.out.println("The array is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```
The TreeSet: [For, Geeks, To, Welcome]
The array is:
For
Geeks
To
Welcome

```

**程序 2:**

```
// Java code to illustrate toArray()

import java.util.*;

public class TreeSetDemo {
    public static void main(String args[])
    {
        // Creating an empty TreeSet
        TreeSet<Integer>
            set = new TreeSet<Integer>();

        // Use add() method to add
        // elements into the TreeSet
        set.add(10);
        set.add(15);
        set.add(30);
        set.add(20);
        set.add(5);
        set.add(25);

        // Displaying the TreeSet
        System.out.println("The TreeSet: "
                           + set);

        // Creating the array and using toArray()
        Object[] arr = set.toArray();

        System.out.println("The array is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```
The TreeSet: [5, 10, 15, 20, 25, 30]
The array is:
5
10
15
20
25
30

```