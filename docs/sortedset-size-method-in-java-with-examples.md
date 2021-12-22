# Java 中的 SortedSet size()方法，示例

> 原文:[https://www . geesforgeks . org/sorted set-size-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedset-size-method-in-java-with-examples/)

**[排序集界面](https://www.geeksforgeeks.org/sortedset-java-examples/)** 的**大小()**方法用于获取排序集的大小或排序集中存在的元素数量。

**语法:**

```
int size()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回**大小**或排序集中存在的元素数量。

**注**:[sorted Set](https://www.geeksforgeeks.org/sortedset-java-examples/)中的 size()方法继承了 Java 中的 [Set 接口](https://www.geeksforgeeks.org/set-in-java/)。

下面的程序说明了 java.util.Set.size()方法:

```
// Java code to illustrate Set.size() method

import java.util.*;

public class SetDemo {
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
        System.out.println("Set: " + set);

        // Displaying the size of the Set
        System.out.println(
            "The size of the SortedSet is: "
            + set.size());
    }
}
```

**输出:**

```
Set: [4, Geeks, To, Welcome]
The size of the SortedSet is: 4

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/set . html # size()](https://docs.oracle.com/javase/7/docs/api/java/util/Set.html#size())