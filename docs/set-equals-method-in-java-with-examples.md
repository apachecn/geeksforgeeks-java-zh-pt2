# 用示例在 Java 中设置 equals()方法

> 原文:[https://www . geesforgeks . org/set-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/set-equals-method-in-java-with-examples/)

**java.util.Set** 类的 **equals()** 方法用于验证对象与集合的相等性并进行比较。如果两个集合的大小相等并且都包含相同的元素，则方法返回 true。

**语法:**

```
public boolean equals(Object o)
```

**参数:**该方法以的**对象为参数，与该集合进行相等性比较。**

**返回值:**如果指定的对象等于这个集合，这个方法返回**真**。

以下是说明**等于()**方法的例子。

**例 1:**

```
// Java program to demonstrate equals()
// method of Set

import java.util.*;

public class GFG {
    public static void main(String[] argv)
    {

        // Creating object of Set
        Set<String> arrset1 = new HashSet<String>();

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
        Set<String> arrset2 = new HashSet<String>();

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
        boolean value = arrset1.equals(arrset2);

        // print the value
        System.out.println("Are both set equal? "
                           + value);
    }
}
```

**输出:**

```
First Set: [A, B, C, D, E]
Second Set: [A, B, C, D, E]
Are both set equal? true

```

**例 2:**

```
// Java program to demonstrate equals()
// method of Set

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {

        // Creating object of Set
        Set<Integer> arrset1 = new HashSet<Integer>();

        // Populating arrset1
        arrset1.add(10);
        arrset1.add(20);
        arrset1.add(30);
        arrset1.add(40);
        arrset1.add(50);

        // print arrset1
        System.out.println("First Set: " + arrset1);

        // Creating another object of Set
        Set<Integer> arrset2 = new HashSet<Integer>();

        // Populating arrset2
        arrset2.add(10);
        arrset2.add(20);
        arrset2.add(30);

        // print arrset2
        System.out.println("Second Set: " + arrset2);

        // comparing first Set to another
        // using equals() method
        boolean value = arrset1.equals(arrset2);

        // print the value
        System.out.println("Are both set equal? "
                           + value);
    }
}
```

**输出:**

```
First Set: [50, 20, 40, 10, 30]
Second Set: [20, 10, 30]
Are both set equal? false

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/set . html # equals(Java . lang . object)](https://docs.oracle.com/javase/7/docs/api/java/util/Set.html#equals(java.lang.Object))