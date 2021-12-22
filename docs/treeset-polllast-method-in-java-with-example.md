# Java 中的 TreeSet pollLast()方法，示例

> 原文:[https://www . geesforgeks . org/treeset-poll last-method-in-Java-with-example/](https://www.geeksforgeeks.org/treeset-polllast-method-in-java-with-example/)

**Java . util . concurrent . treeset**的 **pollLast()** 方法是 Java 中的一个内置函数，它返回检索并移除最后一个(最高的)元素，如果这个集合为空，则返回 null。

**语法:**

```java
public E pollLast()
```

**返回值:**函数返回检索并删除最后一个(最高的)元素，如果该集合为空，则返回 null。

下面的程序说明了 TreeSet.pollLast()方法:

**程序 1:**

```java
// Java program to demonstrate pollLast()
// method of TreeSet

import java.util.*;

class TreeSetpollLastExample1 {
    public static void main(String[] args)
    {
        // Creating a set object
        TreeSet<Integer> set
            = new TreeSet<Integer>();

        // Adding elements to this set
        for (int i = 10; i <= 50; i += 10)
            set.add(i);

        // Printing the content of the set
        System.out.println("Contents of the set: " + set);

        // Retrieving and removing Last element of the set
        System.out.println("The Last element of the set: "
                           + set.pollLast());

        // Printing the content of the set after pollLast()
        System.out.println("Contents of the set after pollLast: "
                           + set);
    }
}
```

**Output:**

```java
Contents of the set: [10, 20, 30, 40, 50]
The Last element of the set: 50
Contents of the set after pollLast: [10, 20, 30, 40]

```

**程序 2:**

```java
// Java program to demonstrate pollLast()
// method of TreeSet

import java.util.*;

class TreeSetpollLastExample2 {
    public static void main(String[] args)
    {
        // Creating a set object
        TreeSet<Integer> set
            = new TreeSet<Integer>();

        // Printing the content of the set
        System.out.println("Contents of the set: "
                           + set);

        // Retrieving and removing Last element of the set
        System.out.println("The Last element of the set: "
                           + set.pollLast());
    }
}
```

**Output:**

```java
Contents of the set: []
The Last element of the set: null

```