# 设置 union()函数|番石榴| Java

> 原文:[https://www . geesforgeks . org/set-union-function-guava-Java/](https://www.geeksforgeeks.org/sets-union-function-guava-java/)

番石榴的**set . union()**返回两个集合并集的 ***不可修改视图*** 。返回的集合包含任一支持集合中包含的所有元素。迭代返回的集合首先迭代集合 1 的所有元素，然后依次迭代集合 2 中不包含在集合 1 中的每个元素。

**语法:**

```
public static <E> 
  Sets.SetView<E> 
    union(Set<? extends E> set1, 
          Set<? extends E> set2)

```

**返回值:**这个方法返回两个集合并集的不可修改的视图。

**例 1:**

```
// Java code to show implementation
// of Guava's Sets.union() method

import com.google.common.collect.Sets;
import java.util.Set;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating first set
        Set<Integer>
            set1 = Sets.newHashSet(1, 2, 3, 4, 5);

        // Creating second set
        Set<Integer>
            set2 = Sets.newHashSet(3, 5, 7, 9);

        // Using Guava's Sets.union() method
        Set<Integer>
            answer = Sets.union(set1, set2);

        // Displaying the union of set set1 and set2
        System.out.println("Set 1: "
                           + set1);
        System.out.println("Set 2: "
                           + set2);
        System.out.println("Set 1 union Set 2: "
                           + answer);
    }
}
```

**Output:**

```
Set 1: [1, 2, 3, 4, 5]
Set 2: [9, 3, 5, 7]
Set 1 union Set 2: [1, 2, 3, 4, 5, 9, 7]

```

**例 2:**

```
// Java code to show implementation
// of Guava's Sets.union() method

import com.google.common.collect.Sets;
import java.util.Set;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating first set
        Set<String>
            set1 = Sets.newHashSet("G", "e", "e", "k", "s");

        // Creating second set
        Set<String>
            set2 = Sets.newHashSet("g", "f", "G", "e");

        // Using Guava's Sets.union() method
        Set<String>
            answer = Sets.union(set1, set2);

        // Displaying the union of set set1 and set2
        System.out.println("Set 1: "
                           + set1);
        System.out.println("Set 2: "
                           + set2);
        System.out.println("Set 1 union Set 2: "
                           + answer);
    }
}
```

**Output:**

```
Set 1: [k, s, e, G]
Set 2: [e, f, g, G]
Set 1 union Set 2: [k, s, e, G, f, g]

```