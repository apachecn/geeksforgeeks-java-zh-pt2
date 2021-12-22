# Java 中的 SortedSet tailSet()方法

> 原文:[https://www . geesforgeks . org/sorted set-tailset-method-in-Java/](https://www.geeksforgeeks.org/sortedset-tailset-method-in-java/)

Java 中 [SortedSet 接口的 tailSet()方法用于返回该集合中元素大于或等于参数 *fromElement* 的部分的视图。](https://www.geeksforgeeks.org/sortedset-java-examples/)

[*   The collection returned by this method is supported by this collection, so the changes in the returned collection are reflected in this collection, and vice versa.*   The collection returned by this method supports all optional collection operations supported by this collection.](https://www.geeksforgeeks.org/sortedset-java-examples/)

**注意**:如果试图插入一个超出其范围的元素，这个方法返回的集合将抛出 *IllegalArgumentException* 。

**语法** :

```
SortedSet tailSet(E fromElement)

```

其中，E 是该集合维护的元素类型。

**参数**:该函数接受单个参数 *fromElement* ，表示返回集合的低端点(含)。

**返回值**:从元素中返回大于等于给定参数*的元素。*

**异常**:

*   [T0】 ClassCastException 【T1]: If the fromElement is incompatible with the comparator of this set (or if the set has no comparator, if the fromElement does not implement compatible), a classcasteexception will be thrown.
*   **null pointer exception** : if the parameter *fromelement* is null, a null pointer exception will be thrown.
*   [T0】 IllegalArgumentException 【T1]: It throws an IllegalArgumentException. This set itself has a restricted range, and the parameter *fromelement* is outside the range boundary.

下面的程序说明了上述方法:

**程序 1** :

```
// A Java program to demonstrate
// working of SortedSet
import java.util.SortedSet;
import java.util.TreeSet;

public class Main {
    public static void main(String[] args)
    {
        // Create a TreeSet and inserting elements
        SortedSet<Integer> s = new TreeSet<>();

        // Adding Element to SortedSet
        s.add(1);
        s.add(5);
        s.add(2);
        s.add(3);
        s.add(9);

        // Returning the set with elements
        // strictly less than the passed value
        System.out.print("Elements greater than or equal to 5 in set are : "
                         + s.tailSet(5));
    }
}
```

**输出:**

```
Elements greater than or equal to 5 in set are : [5, 9]

```

**程序二** :

```
// A Java program to demonstrate
// working of SortedSet
import java.util.SortedSet;
import java.util.TreeSet;

public class Main {
    public static void main(String[] args)
    {
        // Create a TreeSet and inserting elements
        SortedSet<String> s = new TreeSet<>();

        // Adding Element to SortedSet
        s.add("Geeks");
        s.add("For");
        s.add("Geeks");
        s.add("Code");
        s.add("It");

        // Returning the set with elements
        // strictly less than the passed value
        System.out.print("Element greater than or equal to G in set is : "
                         + s.tailSet("G"));
    }
}
```

**输出:**

```
Element greater than or equal to G in set is : [Geeks, It]

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/util/sorted set . html # tailSet(E)](https://docs.oracle.com/javase/10/docs/api/java/util/SortedSet.html#tailSet(E))