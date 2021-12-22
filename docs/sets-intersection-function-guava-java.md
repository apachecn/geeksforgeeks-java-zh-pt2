# 设置交集()函数|番石榴| Java

> 原文:[https://www . geesforgeks . org/set-交集-函数-guava-java/](https://www.geeksforgeeks.org/sets-intersection-function-guava-java/)

番石榴的**set . interface()**返回两个集合的交集的 ***不可修改视图*** 。返回的集合包含两个支持集合包含的所有元素。返回集合的迭代顺序与集合 1 的迭代顺序相匹配。

**语法:**

```
public static <E> 
    Sets.SetView<E> 
        intersection(Set<E> set1, Set<?> set2)

```

**返回值:**这个方法返回两个集合的交集的不可修改的视图。

以下示例说明了集合交集方法的工作原理:

**例 1:**

```
// Java code to show implementation
// of Guava's Sets.intersection() method

import com.google.common.collect.Sets;
import java.util.Set;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating first set
        Set<Integer>
            set1 = Sets.newHashSet(10, 20, 30, 40, 50);

        // Creating second set
        Set<Integer>
            set2 = Sets.newHashSet(30, 50, 70, 90);

        // Using Guava's Sets.intersection() method
        Set<Integer>
            answer = Sets.intersection(set1, set2);

        // Displaying the intersection of set1 and set2
        System.out.println("Set 1: "
                           + set1);
        System.out.println("Set 2: "
                           + set2);
        System.out.println("Set 1 intersection Set 2: "
                           + answer);
    }
}
```

**输出:**

```
Set 1: [40, 10, 50, 20, 30]
Set 2: [50, 90, 30, 70]
Set 1 intersection Set 2: [50, 30]

```

**例 2:**

```
// Java code to show implementation
// of Guava's Sets.intersection() method

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

        // Using Guava's Sets.intersection() method
        Set<String>
            answer = Sets.intersection(set1, set2);

        // Displaying the intersection of set1 and set2
        System.out.println("Set 1: "
                           + set1);
        System.out.println("Set 2: "
                           + set2);
        System.out.println("Set 1 intersection Set 2: "
                           + answer);
    }
}
```

**输出:**

```
Set 1: [k, s, e, G]
Set 2: [e, f, g, G]
Set 1 intersection Set 2: [e, G]

```

**注意:**当 set1 是两个 set 中较小的一个时，返回的视图表现稍好。如果你有理由相信你的一套通常会比另一套小，先通过它。