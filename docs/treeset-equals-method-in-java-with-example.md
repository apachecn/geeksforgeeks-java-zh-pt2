# Java 中的 TreeSet 等于()方法，示例

> 原文:[https://www . geesforgeks . org/treeset-equals-method-in-Java-with-example/](https://www.geeksforgeeks.org/treeset-equals-method-in-java-with-example/)

**java.util.TreeSet** 类的 **equals()** 方法用于将指定的对象与该集合进行相等比较。当且仅当指定的对象也是集合，两个集合具有相同的大小，并且两个集合中所有对应的元素对相等时，返回 true。(两个元素 e1 和 e2 相等，如果(e1==null？e2==null : e1.equals(e2))。)换句话说，如果两个集合包含相同顺序的相同元素，则它们被定义为相等。

**语法:**

```java
public boolean equals(Object o)
```

**参数:**该方法以的**对象为参数，与该集合进行相等性比较。**

**返回值:**如果指定的对象等于这个集合，这个方法返回**真**。

以下是说明**等于()**方法的例子。

**例 1:**

```java
// Java program to demonstrate equals()
// method of TreeSet

import java.util.*;

public class GFG {
    public static void main(String[] argv)
    {

        // Creating object of TreeSet<String>
        TreeSet<String>
            set1 = new TreeSet<String>();

        // Populating set1
        set1.add("A");
        set1.add("B");
        set1.add("C");
        set1.add("D");
        set1.add("E");

        // print set1
        System.out.println("First TreeSet: "
                           + set1);

        // Creating another object of TreeSet<String>
        TreeSet<String>
            set2 = new TreeSet<String>();

        // Populating set2
        set2.add("A");
        set2.add("B");
        set2.add("C");
        set2.add("D");
        set2.add("E");

        // print set2
        System.out.println("Second TreeSet: "
                           + set2);

        // comparing first TreeSet to another
        // using equals() method
        boolean value
            = set1.equals(set2);

        // print the value
        System.out.println("Are both set equal: "
                           + value);
    }
}
```

**Output:**

```java
First TreeSet: [A, B, C, D, E]
Second TreeSet: [A, B, C, D, E]
Are both set equal: true

```

**例 2:**

```java
// Java program to demonstrate equals()
// method of TreeSet

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {

        // Creating object of TreeSet
        TreeSet<Integer>
            set1 = new TreeSet<Integer>();

        // Populating set1
        set1.add(10);
        set1.add(20);
        set1.add(30);
        set1.add(40);
        set1.add(50);

        // print set1
        System.out.println("First TreeSet: "
                           + set1);

        // Creating another object of TreeSet
        TreeSet<Integer>
            set2 = new TreeSet<Integer>();

        // Populating set2
        set2.add(10);
        set2.add(20);
        set2.add(30);

        // print set2
        System.out.println("Second TreeSet: "
                           + set2);

        // comparing first TreeSet to another
        // using equals() method
        boolean value = set1.equals(set2);

        // print the value
        System.out.println("Are both set equal: "
                           + value);
    }
}
```

**Output:**

```java
First TreeSet: [10, 20, 30, 40, 50]
Second TreeSet: [10, 20, 30]
Are both set equal: false

```