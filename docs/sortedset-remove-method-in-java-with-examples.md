# Java 中的 SortedSet remove()方法，示例

> 原文:[https://www . geesforgeks . org/sorted set-remove-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedset-remove-method-in-java-with-examples/)

[**排序集界面**](https://www.geeksforgeeks.org/sortedset-java-examples/) 的**移除(对象 O)** 方法用于从该排序集中移除特定元素。

**语法:**

```java
boolean remove(Object O)
```

**参数:**参数 *O* 属于此排序集维护的元素类型，并指定要从该集中删除的元素。

**返回值:**如果集合中存在指定的元素，该方法返回真，否则返回假。

**注**:[sorted Set](https://www.geeksforgeeks.org/sortedset-java-examples/)中的 remove()方法继承了 Java 中的 [Set 接口](https://www.geeksforgeeks.org/set-in-java/)。

下面的程序说明了 Java . util . sorted set . remove(Object O)方法:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate
// SortedSet.remove() method

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

        // Removing elements
        // using remove() method
        set.remove("Geeks");
        set.remove("4");
        set.remove("Welcome");

        // Displaying the Set after removal
        System.out.println(
            "SortedSet after "
            + "removing elements: "
            + set);
    }
}
```

**Output:** 

```java
SortedSet: [4, Geeks, To, Welcome]
SortedSet after removing elements: [To]
```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/set . html # remove(Java . lang . object)](https://docs.oracle.com/javase/7/docs/api/java/util/Set.html#remove(java.lang.Object))