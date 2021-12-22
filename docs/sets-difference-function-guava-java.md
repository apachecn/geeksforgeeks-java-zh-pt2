# 设置差()函数|番石榴| Java

> 原文:[https://www . geesforgeks . org/set-difference-function-guava-Java/](https://www.geeksforgeeks.org/sets-difference-function-guava-java/)

番石榴的**set . difference()**返回两个 set 之差的 ***不可修改视图*** 。

**语法:**

```java
public static <E> 
  Sets.SetView<E> 
    difference(Set<E> set1,
               Set<?> set2)

```

**返回值:**该方法返回一个集合，该集合包含集合 1 包含的所有元素，集合 2 不包含所有元素。

**注意:** Set2 也可能包含 set1 中不存在的元素，这些被简单忽略。返回集合的迭代顺序与集合 1 的迭代顺序相匹配。

**例 1:**

```java
// Java code to show implementation of
// Guava's Sets.difference() method

import com.google.common.collect.Sets;
import java.util.Set;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Creating first set named set1
        Set<Integer>
            set1 = Sets.newHashSet(1, 2, 3, 4, 5, 6);

        // Creating second set named set2
        Set<Integer>
            set2 = Sets.newHashSet(1, 3, 5, 7);

        // Using Guava's Sets.difference() method
        Set<Integer>
            diff = Sets.difference(set1, set2);

        // Displaying the unmodifiable view of
        // the difference of two sets.
        System.out.println("Set 1: "
                           + set1);
        System.out.println("Set 2: "
                           + set2);
        System.out.println("Difference between "
                           + "Set 1 and Set 2: "
                           + diff);
    }
}
```

**Output:**

```java
Set 1: [1, 2, 3, 4, 5, 6]
Set 2: [1, 3, 5, 7]
Difference between Set 1 and Set 2: [2, 4, 6]

```

**例 2 :**

```java
// Java code to show implementation of
// Guava's Sets.difference() method

import com.google.common.collect.Sets;
import java.util.Set;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating first set named set1
        Set<String>
            set1 = Sets
                       .newHashSet("H", "E", "L", "L", "O", "G");

        // Creating second set named set2
        Set<String>
            set2 = Sets
                       .newHashSet("L", "I", "K", "E", "G");

        // Using Guava's Sets.difference() method
        Set<String>
            diff = Sets.difference(set1, set2);

        // Displaying the unmodifiable view of
        // the difference of two sets.
        System.out.println("Set 1: "
                           + set1);
        System.out.println("Set 2: "
                           + set2);
        System.out.println("Difference between "
                           + "Set 1 and Set 2: "
                           + diff);
    }
}
```

**Output:**

```java
Set 1: [E, G, H, L, O]
Set 2: [I, K, L, E, G]
Difference between Set 1 and Set 2: [H, O]

```