# Java 中的 SortedSet equals()方法，示例

> 原文:[https://www . geesforgeks . org/sorted set-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedset-equals-method-in-java-with-examples/)

[**Java . util . SortedSet**](https://www.geeksforgeeks.org/sortedset-java-examples/)类的 **equals()** 方法用于验证一个对象与一个 sorted set 的相等性并进行比较。如果两个排序集的大小相等并且都包含相同的元素，则该方法返回 true。

**语法:**

```java
public boolean equals(Object o)
```

**参数:**该方法以的**对象为参数，与该集合进行相等性比较。**

**返回值:**如果指定的对象等于这个集合，这个方法返回**真**。

**注**:[sorted Set](https://www.geeksforgeeks.org/sortedset-java-examples/)中的 equals()方法继承了 Java 中的 [Set 接口](https://www.geeksforgeeks.org/set-in-java/)。

以下是说明**等于()**方法的例子。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate equals()
// method of SortedSet

import java.util.*;

public class GFG {
    public static void main(String[] argv)
    {

        // Creating object of Set
        SortedSet<String> arrset1
            = new TreeSet<String>();

        // Populating arrset1
        arrset1.add("A");
        arrset1.add("B");
        arrset1.add("C");
        arrset1.add("D");
        arrset1.add("E");

        // print arrset1
        System.out.println("First Set: "
                           + arrset1);

        // Creating another object of Set
        SortedSet<String> arrset2
            = new TreeSet<String>();

        // Populating arrset2
        arrset2.add("A");
        arrset2.add("B");
        arrset2.add("C");
        arrset2.add("D");
        arrset2.add("E");

        // print arrset2
        System.out.println("Second Set: "
                           + arrset2);

        // comparing first Set to another
        // using equals() method
        boolean value
            = arrset1.equals(arrset2);

        // print the value
        System.out.println("Are both set equal? "
                           + value);
    }
}
```

**Output:** 

```java
First Set: [A, B, C, D, E]
Second Set: [A, B, C, D, E]
Are both set equal? true
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// equals() method of Sorted Set

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {

        // Creating object of Set
        SortedSet<Integer> arrset1
            = new TreeSet<Integer>();

        // Populating arrset1
        arrset1.add(10);
        arrset1.add(20);
        arrset1.add(30);
        arrset1.add(40);
        arrset1.add(50);

        // print arrset1
        System.out.println("First Set: "
                           + arrset1);

        // Creating another object of Set
        SortedSet<Integer> arrset2
            = new TreeSet<Integer>();

        // Populating arrset2
        arrset2.add(10);
        arrset2.add(20);
        arrset2.add(30);

        // print arrset2
        System.out.println("Second Set: "
                           + arrset2);

        // comparing first Set to another
        // using equals() method
        boolean value
            = arrset1.equals(arrset2);

        // print the value
        System.out.println("Are both set equal? "
                           + value);
    }
}
```

**输出:**

```java
First Set: [10, 20, 30, 40, 50]
Second Set: [10, 20, 30]
Are both set equal? false
```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/set . html # equals(Java . lang . object)](https://docs.oracle.com/javase/7/docs/api/java/util/Set.html#equals(java.lang.Object))