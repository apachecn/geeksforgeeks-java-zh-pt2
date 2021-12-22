# 用示例排序 Java 中的 Set 接口

> 原文:[https://www.geeksforgeeks.org/sortedset-java-examples/](https://www.geeksforgeeks.org/sortedset-java-examples/)

出现在 [java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包中的 SortedSet 接口扩展了出现在[收集框架](https://www.geeksforgeeks.org/collections-in-java-2/)中的 Set 接口。这是一个实现数学集合的接口。此接口包含从 Set 接口继承的方法，并添加了一个功能，用于存储此接口中的所有元素，以便以排序的方式进行存储。

![Set-TreeSet-SortedSet-In-Java-Collection](img/c82baacf195cb0ef187cc6ee2389de53.png)

在上图中，可导航集扩展了排序集界面。由于集合不保留插入顺序，可导航的集合接口提供了在集合中导航的实现。实现可导航集的类是 TreeSet，它是一个自平衡树的实现。因此，这个界面为我们提供了一种在这个树中导航的方法。

**声明:**sorted set 接口声明为:

> 公共接口排序集扩展集

**排序集示例:**

```
// Java program to demonstrate the
// Sorted Set
import java.util.*;

class SortedSetExample{

    public static void main(String[] args)
    {
        SortedSet<String> ts
            = new TreeSet<String>();

        // Adding elements into the TreeSet
        // using add()
        ts.add("India");
        ts.add("Australia");
        ts.add("South Africa");

        // Adding the duplicate
        // element
        ts.add("India");

        // Displaying the TreeSet
        System.out.println(ts);

        // Removing items from TreeSet
        // using remove()
        ts.remove("Australia");
        System.out.println("Set after removing "
                           + "Australia:" + ts);

        // Iterating over Tree set items
        System.out.println("Iterating over set:");
        Iterator<String> i = ts.iterator();
        while (i.hasNext())
            System.out.println(i.next());
    }
}
```

**Output:**

```
[Australia, India, South Africa]
Set after removing Australia:[India, South Africa]
Iterating over set:
India
South Africa

```

**注意:**排序集合的所有元素必须实现[可比接口](https://www.geeksforgeeks.org/comparable-vs-comparator-in-java/)(或被指定的比较器接受)，并且所有这些元素必须相互可比。相互比较简单地说就是两个对象相互接受对方作为它们的 compareTo 方法的参数。

**创建排序集对象**

由于排序集是一个[接口](https://www.geeksforgeeks.org/interfaces-in-java/)，因此不能创建排序集类型的对象。我们总是需要一个扩展这个列表的类来创建一个对象。此外，在 Java 1.5 中引入[泛型](https://www.geeksforgeeks.org/generics-in-java/)后，可以限制可存储在 SortedSet 中的对象类型。这种类型安全集合可以定义为:

> // Obj 是要存储在 sorted set
> sorted set<Obj>set = new TreeSet<Obj>()；

### 对排序集执行各种操作

由于 SortedSet 是一个接口，它只能与实现该接口的类一起使用。TreeSet 是实现 SortedSet 接口的类。现在，让我们看看如何在 TreeSet 上执行一些常用的操作。

**1。添加元素:**为了给 SortedSet 添加一个元素，我们可以使用 [add()方法。](https://www.geeksforgeeks.org/sortedset-add-method-in-java-with-examples/)但是，插入顺序不会保留在树集中。在内部，对于每个元素，值都是按升序进行比较和排序的。我们需要注意，重复的元素是不允许的，所有重复的元素都会被忽略。此外，排序集不接受空值。

```
// Java code to demonstrate
// the working of SortedSet
import java.util.*;

class GFG {

    public static void main(String[] args)
    {
        SortedSet<String> ts
            = new TreeSet<String>();

        // Elements are added using add() method
        ts.add("A");
        ts.add("B");
        ts.add("C");
        ts.add("A");

        System.out.println(ts);
    }
}
```

**Output:**

```
[A, B, C]

```

**2。访问元素:**添加元素后，如果想访问元素，可以使用内置的方法，如 [contains()](https://www.geeksforgeeks.org/sortedset-contains-method-in-java-with-examples/) 、 [first()](https://www.geeksforgeeks.org/sortedset-contains-method-in-java-with-examples/) 、 [last()](https://www.geeksforgeeks.org/sortedset-last-method-in-java/) 等。

```
// Java code to demonstrate
// the working of SortedSet

import java.util.*;
class GFG {

    public static void main(String[] args)
    {
        SortedSet<String> ts
            = new TreeSet<String>();

        // Elements are added using add() method
        ts.add("A");
        ts.add("B");
        ts.add("C");
        ts.add("A");

        System.out.println("Sorted Set is " + ts);

        String check = "D";

        // Check if the above string exists in
        // the SortedSet or not
        System.out.println("Contains " + check
                           + " " + ts.contains(check));

        // Print the first element in
        // the SortedSet
        System.out.println("First Value " + ts.first());

        // Print the last element in
        // the SortedSet
        System.out.println("Last Value " + ts.last());
    }
}
```

**Output:**

```
Sorted Set is [A, B, C]
Contains D false
First Value A
Last Value C

```

**3。移除值:**可以使用[移除()方法](https://www.geeksforgeeks.org/sortedset-remove-method-in-java-with-examples/)从排序集中移除值。

```
// Java code to demonstrate
// the working of SortedSet

import java.util.*;
class GFG{

    public static void main(String[] args)
    {
        SortedSet<String> ts
            = new TreeSet<String>();

        // Elements are added using add() method
        ts.add("A");
        ts.add("B");
        ts.add("C");
        ts.add("B");
        ts.add("D");
        ts.add("E");

        System.out.println("Initial TreeSet " + ts);

        // Removing the element b
        ts.remove("B");

        System.out.println("After removing element " + ts);
    }
}
```

**Output:**

```
Initial TreeSet [A, B, C, D, E]
After removing element [A, C, D, E]

```

**4。迭代排序集:**有多种方法迭代排序集。最著名的一个是使用[增强为循环。](https://www.geeksforgeeks.org/loops-in-java/)

```
// Java code to demonstrate
// the working of SortedSet

import java.util.*;
class GFG
 { 
    public static void main(String[] args)
    {
        SortedSet<String> ts
            = new TreeSet<String>();

        // Elements are added using add() method
        ts.add("C");
        ts.add("D");
        ts.add("E");
        ts.add("A");
        ts.add("B");
        ts.add("Z");

        // Iterating though the SortedSet
        for (String value : ts)
            System.out.print(value
                             + ", ");
        System.out.println();
    }
}
```

**Output:**

```
A, B, C, D, E, Z,

```

***实现 SortedSet 接口的类是 TreeSet。**T3】*

**[TreeSet:](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)** TreeSet 类在 collections 框架中实现，是 SortedSet 接口的实现，SortedSet 扩展了 [Set 接口](https://www.geeksforgeeks.org/set-in-java/)。它的行为就像一个简单的集合，只是它以排序的格式存储元素。TreeSet 使用树形数据结构进行存储。对象以排序的升序存储。但是我们可以使用方法[treeset . Degending Terrar()](https://www.geeksforgeeks.org/treeset-descendingiterator-method-in-java-with-examples/)进行降序迭代。让我们看看如何使用这个类创建 sortedset 对象。

```
// Java program to demonstrate the
// creation of SortedSet object using
// the TreeSet class

import java.util.*;

class GFG {

    public static void main(String[] args)
    {
        SortedSet<String> ts
            = new TreeSet<String>();

        // Adding elements into the TreeSet
        // using add()
        ts.add("India");
        ts.add("Australia");
        ts.add("South Africa");

        // Adding the duplicate
        // element
        ts.add("India");

        // Displaying the TreeSet
        System.out.println(ts);

        // Removing items from TreeSet
        // using remove()
        ts.remove("Australia");
        System.out.println("Set after removing "
                           + "Australia:" + ts);

        // Iterating over Tree set items
        System.out.println("Iterating over set:");
        Iterator<String> i = ts.iterator();
        while (i.hasNext())
            System.out.println(i.next());
    }
}
```

**Output:**

```
[Australia, India, South Africa]
Set after removing Australia:[India, South Africa]
Iterating over set:
India
South Africa

```

### 排序集合接口的方法

以下是 SortedSet 接口中存在的方法。这里“*”表示方法是[设置界面](https://www.geeksforgeeks.org/set-in-java/)的一部分。

| 方法 | 描述 |
| **[*添加(元素)](https://www.geeksforgeeks.org/sortedset-add-method-in-java-with-examples/)** | 此方法用于向集合中添加特定元素。只有当集合中没有指定的元素时，函数才会添加元素，否则，如果集合中已经有元素，函数将返回 False。 |
| **[*addAll(集合)](https://www.geeksforgeeks.org/sortedset-addall-method-in-java-with-examples/)** | 此方法用于将上述集合中的所有元素追加到现有集合中。元素是随机添加的，没有遵循任何特定的顺序。 |
| **[*晴()](https://www.geeksforgeeks.org/sortedset-clear-method-in-java-with-examples/)** | 此方法用于从集合中移除所有元素，但不删除集合。集合的引用仍然存在。 |
| **[【比较仪()](https://www.geeksforgeeks.org/treeset-comparator-method-in-java/)** | 此方法返回用于对该集合中的元素进行排序的比较器，如果该集合使用其元素的自然排序，则返回 null。 |
| **[*包含(元素)](https://www.geeksforgeeks.org/sortedset-contains-method-in-java-with-examples/)** | 此方法用于检查集合中是否存在特定元素。 |
| **[*containsAll(集合)](https://www.geeksforgeeks.org/sortedset-containsall-method-in-java-with-examples/)** | 此方法用于检查集合是否包含给定集合中存在的所有元素。如果集合包含所有元素，则此方法返回 true 如果缺少任何元素，则返回 false。 |
| **[第()](https://www.geeksforgeeks.org/sortedset-first-method-in-java/)** | 此方法返回该集合中的第一个(最低的)元素。 |
| **[【hashcode()](https://www.geeksforgeeks.org/sortedset-hashcode-method-in-java-with-examples/)** | 此方法用于获取该集合实例的哈希码值。它返回一个整数值，该整数值是该集合实例的哈希码值。 |
| **[耳机(元素)](https://www.geeksforgeeks.org/sortedset-headset-method-in-java/)** | 此方法返回的元素少于排序集中的元素。 |
| **[*isEmpty()](https://www.geeksforgeeks.org/sortedset-isempty-method-in-java-with-examples/)** | 此方法用于检查排序集是否为空。 |
| **[最后()](https://www.geeksforgeeks.org/sortedset-last-method-in-java/)** | 此方法返回集合中最后(最高)的元素。 |
| **[*移除(元素)](https://www.geeksforgeeks.org/sortedset-remove-method-in-java-with-examples/)** | 此方法用于从集合中移除给定的元素。如果集合中存在指定的元素，此方法返回真，否则返回假。 |
| **[*removeAll(集合)](https://www.geeksforgeeks.org/sortedset-removeall-method-in-java-with-examples/)** | 此方法用于从集合中移除集合中存在的所有元素。如果此集合因调用而改变，则此方法返回 true。 |
| **[*零售(集合)](https://www.geeksforgeeks.org/sortedset-retainall-method-in-java-with-example/)** | 此方法用于保留给定集合中提到的集合中的所有元素。如果此集合因调用而改变，则此方法返回 true。 |
| **[*大小()](https://www.geeksforgeeks.org/sortedset-size-method-in-java-with-example/)** | 此方法用于获取集合的大小。这将返回一个表示元素数量的整数值。 |
| **[【子集(元素 1、元素 2)](https://www.geeksforgeeks.org/sortedset-subset-method-in-java/)** | 此方法从包含 element1 和 element2 之间的元素的集合中返回一个已排序的子集。 |
| **[尾套(元素)](https://www.geeksforgeeks.org/sortedset-tailset-method-in-java/)** | 此方法返回大于或等于排序集中存在的元素的元素。 |
| **[* toaarray()](https://www.geeksforgeeks.org/sortedset-toarray-method-in-java-with-example/)** | 此方法用于形成与集合元素相同元素的数组。 |