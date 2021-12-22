# 用示例在 Java 中设置迭代器()方法

> 原文:[https://www . geesforgeks . org/set-iterator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/set-iterator-method-in-java-with-examples/)

java.util.Set.iterator()方法用于返回与集合具有相同元素的迭代器。元素从集合中随机返回。

**语法:**

```java
Iterator *iterate_value* = Set.iterator();

```

**参数:**函数不取任何参数。

**返回值:**方法迭代集合的元素并返回值(迭代器)。

下面程序举例说明了 java.util.Set.iterator()方法:

```java
// Java code to illustrate iterator()

import java.util.*;

public class SetDemo {
    public static void main(String args[])
    {
        // Creating an empty Set
        Set<String> set = new HashSet<String>();

        // Use add() method to add elements into the Set
        set.add("Welcome");
        set.add("To");
        set.add("Geeks");
        set.add("4");
        set.add("Geeks");

        // Displaying the Set
        System.out.println("Set: " + set);

        // Creating an iterator
        Iterator value = set.iterator();

        // Displaying the values after iterating through the iterator
        System.out.println("The iterator values are: ");
        while (value.hasNext()) {
            System.out.println(value.next());
        }
    }
}
```

**输出:**

```java
Set: [4, Geeks, Welcome, To]
The iterator values are: 
4
Geeks
Welcome
To

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/set . html # iterator()](https://docs.oracle.com/javase/7/docs/api/java/util/Set.html#iterator())