# 设置 powerSet()功能|番石榴| Java

> 原文:[https://www . geesforgeks . org/set-power set-function-guava-Java/](https://www.geeksforgeeks.org/sets-powerset-function-guava-java/)

番石榴的**set . power set()**返回集合的所有可能子集的集合。

**语法:**

```java
public static <E> 
  Set<Set<E>> 
    powerSet(Set<E> set)

```

这里，*集合*是构成幂集的元素集合。

**返回值:**这个方法返回幂集，作为不可变集合的不可变集合。

**异常:**

*   **IllegalArgumentException:** If the set has more than 30 unique elements, it will cause the size of the power set to exceed the int range.
*   **空指针异常:**嘿嘿嘿嘿嘿嘿空值。

**注:**空集的幂集不是空集，而是包含空集的一元集。

**例 1:**

```java
// Java code to return the set of
// all possible subsets of a set

import com.google.common.collect.Sets;
import java.util.Set;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a set
        Set<Integer>
            set = Sets.newHashSet(1, 2, 3);

        // powerSet to store all subsets of a set
        Set<Set<Integer> >
            powerSet = Sets.powerSet(set);

        // Displaying all possible subsets of a set
        for (Set<Integer> s : powerSet)
            System.out.println(s);
    }
}
```

**输出:**

```java
[]
[1]
[2]
[1, 2]
[3]
[1, 3]
[2, 3]
[1, 2, 3]

```

**例 2:**

```java
// Java code to return the set of
// all possible subsets of a set

import com.google.common.collect.Sets;
import java.util.Set;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a set
        Set<String>
            set = Sets.newHashSet("G", "F", "g");

        // powerSet to store all subsets of a set
        Set<Set<String> >
            powerSet = Sets.powerSet(set);

        // Displaying all possible subsets of a set
        for (Set<String> s : powerSet)
            System.out.println(s);
    }
}
```

**输出:**

```java
[]
[F]
[G]
[F, G]
[g]
[F, g]
[G, g]
[F, G, g]

```

**注:**n 大小集合的幂集为 2^n 大小，其内存使用量仅为 **O(n)** 。当构造幂集时，只复制输入集。只有当幂集迭代时，才会创建单独的子集，这些子集本身只占用少量的恒定内存。