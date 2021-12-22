# 用示例

在 Java 中设置 Array()方法

> 原文:[https://www . geesforgeks . org/set-to array-method-in-Java-with-example/](https://www.geeksforgeeks.org/set-toarray-method-in-java-with-example/)

**Java Set** 的 **toArray()** 方法用于形成与 Set 相同元素的数组。基本上，它将集合中的所有元素复制到一个新数组中。
**语法:**

```
Object[] toArray()
```

**参数:**该方法取可选参数。如果我们提供我们想要的对象数组的类型，我们可以把它作为一个参数传递。例如:set.toArray(新的 Integer[0])返回一个 Integer 类型的数组，我们也可以像 set.toArray(新的 Integer[size])那样做，其中 size 是结果数组的大小。按照前一种方式进行，因为所需的大小是在内部分配的。
**返回值:**该方法返回一个包含与集合相似元素的数组。
以下程序说明了 Set.toArray()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate toArray()

import java.util.*;

public class SetDemo {
    public static void main(String args[])
    {
        // Creating an empty Set
        Set<String> abs_col = new HashSet<String>();

        // Use add() method to add
        // elements into the Set
        abs_col.add("Welcome");
        abs_col.add("To");
        abs_col.add("Geeks");
        abs_col.add("For");
        abs_col.add("Geeks");

        // Displaying the Set
        System.out.println("The Set: "
                           + abs_col);

        // Creating the array and using toArray()
        Object[] arr = abs_col.toArray();

        System.out.println("The array is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:** 

```
The Set: [Geeks, For, Welcome, To]
The array is:
Geeks
For
Welcome
To
```

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate toArray()

import java.util.*;

public class SetDemo {
    public static void main(String args[])
    {
        // Creating an empty Set
        Set<Integer> abs_col = new HashSet<Integer>();

        // Use add() method to add
        // elements into the Set
        abs_col.add(10);
        abs_col.add(15);
        abs_col.add(30);
        abs_col.add(20);
        abs_col.add(5);
        abs_col.add(25);

        // Displaying the Set
        System.out.println("The Set: " + abs_col);

        // Creating the array and using toArray()
        Integer[] arr = abs_col.toArray(new Integer[0]);

        System.out.println("The array is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:** 

```
The Set: [20, 5, 25, 10, 30, 15]
The array is:
20
5
25
10
30
15
```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/set . html # to array()](https://docs.oracle.com/javase/7/docs/api/java/util/Set.html#toArray())