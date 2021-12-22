# Java 中的 SortedSet hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/sorted set-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedset-hashcode-method-in-java-with-examples/)

Java 中 **[SortedSet](https://www.geeksforgeeks.org/sortedset-java-examples/)** 的 **hashCode()** 方法用于获取 SortedSet 这个实例的 hashCode 值。它返回一个整数值，这是 SortedSet 实例的 hashCode 值。

**语法:**

```java
public int hashCode()
```

**参数:**该功能没有参数。

**返回:**该方法返回一个**整数值**，这是该集合实例的哈希值。

**注**:[sorted Set](https://www.geeksforgeeks.org/sortedset-java-examples/)中的 hashCode()方法继承了 Java 中的 [Set 接口](https://www.geeksforgeeks.org/set-in-java/)。

以下示例说明了 SortedSet.hashCode()方法:

**例 1:**

```java
// Java code to demonstrate the working of
// hashCode() method in SortedSet

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // creating an Set
        SortedSet<Integer> arr
            = new TreeSet<Integer>();

        // using add() to initialize values
        // [1, 2, 3, 4]
        arr.add(1);
        arr.add(2);
        arr.add(3);
        arr.add(4);

        // print Set
        System.out.println("Set: " + arr);

        // Get the hashCode value
        // using hashCode() value
        System.out.println("HashCode value: "
                           + arr.hashCode());
    }
}
```

**输出:**

```java
Set: [1, 2, 3, 4]
HashCode value: 10

```

**例 2:**

```java
// Java code to demonstrate the working of
// hashCode() method in Set

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // creating an Set
        SortedSet<String> arr
            = new TreeSet<String>();

        // using add() to initialize values
        // [Geeks, For, ForGeeks, GeeksForGeeks]
        arr.add("Geeks");
        arr.add("For");
        arr.add("ForGeeks");
        arr.add("GeeksForGeeks");

        // print Set
        System.out.println("Set: " + arr);

        // Get the hashCode value
        // using hashCode() value
        System.out.println("HashCode value: "
                           + arr.hashCode());
    }
}
```

**输出:**

```java
Set: [For, ForGeeks, Geeks, GeeksForGeeks]
HashCode value: -482506029

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/set . html # hashCode()](https://docs.oracle.com/javase/7/docs/api/java/util/Set.html#hashCode())