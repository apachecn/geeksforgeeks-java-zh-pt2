# Java 中的 TreeSet pollFirst()方法

> 原文:[https://www . geesforgeks . org/treeset-poll first-method-in-Java/](https://www.geeksforgeeks.org/treeset-pollfirst-method-in-java/)

Java 中 [TreeSet 的 pollFirst()方法用于检索并移除第一个(最低的)元素，如果该 TreeSet 为空，则返回 null。
**语法:**](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)

```java
E pollFirst()

```

其中，E 是这个 TreeSet 容器维护的元素类型。
**参数:**该函数不接受任何参数。
**返回类型:**如果 TreeSet 不为空，则返回 Treeset 的第一个元素，否则返回 null。
下面的程序说明了 Java 中的 pollFirst()方法:

**例 1**

```java
// A Java program to demonstrate
// pollFirst() method of TreeSet

import java.util.TreeSet;

public class GFG {
    public static void main(String[] args)
    {
        // creating TreeSet
        TreeSet<Integer> ts = new TreeSet<Integer>();

        // adding element to the TreeSet
        ts.add(0);
        ts.add(1);
        ts.add(2);
        ts.add(3);
        ts.add(4);
        ts.add(5);
        ts.add(6);

        // before removing element
        System.out.println("Before removing " + 
                   "element from TreeSet: " + ts);

        // first element is removed
        System.out.println("First lowest element " + 
                 "removed is : " + ts.pollFirst());
        System.out.println("After removing element" + 
                             " from TreeSet: " + ts);
    }
}
```

**Output:**

```java
Before removing element from TreeSet: [0, 1, 2, 3, 4, 5, 6]
First lowest element removed is : 0
After removing element from TreeSet: [1, 2, 3, 4, 5, 6]

```