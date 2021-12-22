# Java 中的 TreeSet

> 原文:[https://www . geesforgeks . org/treeset-in-Java-with-examples/](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)

TreeSet 是 Java 中 [SortedSet 接口](https://www.geeksforgeeks.org/sortedset-java-examples/)最重要的实现之一，它使用[树](https://www.geeksforgeeks.org/binary-tree-data-structure/)进行存储。无论是否提供明确的[比较器](https://www.geeksforgeeks.org/comparator-interface-java/)，元素的顺序都由一组使用它们的自然顺序来维护。如果要正确实现[设置界面](https://www.geeksforgeeks.org/set-in-java/)，这必须与 equals 一致。

![](img/31b0e27f7605fef98b55045c08b0df6c.png)

它也可以由设置创建时提供的比较器排序，具体取决于使用的构造函数。树集通过继承[抽象集类](https://www.geeksforgeeks.org/abstractset-class-in-java-with-examples/)实现了[导航集接口](https://www.geeksforgeeks.org/navigableset-java-examples/)。

![Set-TreeSet-SortedSet-In-Java-Collection](img/c82baacf195cb0ef187cc6ee2389de53.png)

从上图可以清楚地看到，可导航集扩展了排序集界面。由于集合不保留插入顺序，可导航的集合接口提供了在集合中导航的实现。实现可导航集的类是 TreeSet，它是一个自平衡树的实现。因此，这个界面为我们提供了一种在这个树中导航的方法。

> **注:**
> 
> *   当且仅当相应的类实现了一个**可比接口**时，一个对象被称为可比较的。
> *   [String](https://www.geeksforgeeks.org/string-class-in-java/) 类和所有的[包装器类](https://www.geeksforgeeks.org/wrapper-classes-java/)已经实现了 compatible 接口，但是 [StringBuffer 类](https://www.geeksforgeeks.org/stringbuffer-class-in-java/)实现了 compatible 接口。因此，在上面的例子中，我们没有得到*类异常*。
> *   对于一个空的树集合，当试图插入 null 作为第一个值时，将会得到 JDK 7 的 NPE。从 JDK 7 开始，TreeSet 根本不接受 null。然而，直到 JDK 6，null 被接受为第一个值，但是在 TreeSet 中插入更多的 null 值会导致 NullPointerException。因此，它被认为是一个 bug，因此在 JDK 7 中被删除。
> *   TreeSet 是存储大量排序信息的绝佳选择，这些信息由于其更快的访问和检索时间而应该被快速访问。
> *   向树集中插入空值会引发[NullPointRexception](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)，因为在插入空值时，它会与现有元素进行比较，空值不能与任何值进行比较。

【TreeSet 内部是如何工作的？

TreeSet 基本上是一个自平衡二叉查找树的实现，就像[红黑树](https://www.geeksforgeeks.org/red-black-tree-set-1-introduction-2/)。因此，像添加、删除和搜索这样的操作需要 O(log(N))个时间。原因是，在自平衡树中，确保树的高度对于所有操作始终为 O(log(N))。因此，为了存储庞大的排序数据并对其执行操作，这被认为是最有效的数据结构之一。然而，像按排序顺序打印 N 个元素这样的操作需要 O(N)个时间。

**现在让我们在继续之前讨论同步树集。**树集的实现不同步。这意味着，如果多个线程同时访问一个树集合，并且至少有一个线程修改了该集合，那么它必须在外部同步。这通常是通过同步一些自然地[封装了](https://www.geeksforgeeks.org/encapsulation-in-java/)集合的对象来实现的。如果不存在这样的对象，应该使用[collections . synchronizedstoredset](https://www.geeksforgeeks.org/collections-synchronizedsortedset-method-in-java-with-examples/)方法“包装”该集合。这最好在创建时完成，以防止对集合的意外非同步访问。可以通过如下方式实现:

```java
TreeSet ts = new TreeSet(); 
Set syncSet = Collections.synchronziedSet(ts); 
```

**TreeSet 类的构造函数如下:**

为了创建一个树集合，我们需要创建一个树集合类的对象。TreeSet 类由各种构造函数组成，这些构造函数允许创建 TreeSet。以下是此类中可用的构造函数:

*   **TreeSet():** 此构造函数用于构建一个空的 TreeSet 对象，其中的元素将按照默认的自然排序顺序进行存储。

**语法:**如果我们希望创建一个名为 ts 的空树集，那么它可以创建为:

```java
TreeSet ts = new TreeSet(); 
```

*   **TreeSet(Comparator):** 这个构造函数用来构建一个空的 TreeSet 对象，其中的元素需要一个排序顺序的外部规范。

**语法:**如果我们希望创建一个具有外部排序现象的名为 ts 的空树集，那么，它可以创建为:

```java
TreeSet ts = new TreeSet(Comparator comp); 
```

*   **TreeSet(Collection):** 此构造函数用于构建包含给定集合中所有元素的 TreeSet 对象，其中元素将以默认的自然排序顺序存储。简而言之，当需要从任何 Collection 对象到 TreeSet 对象的任何转换时，都会使用此构造函数。

**语法:**如果我们希望创建一个名为 ts 的树集，那么，它可以如下创建:

```java
TreeSet t = new TreeSet(Collection col);  
```

*   **TreeSet(SortedSet):** 该构造函数用于构建包含给定 [sortedset](https://www.geeksforgeeks.org/sortedset-java-examples/) 中所有元素的 TreeSet 对象，其中元素将以默认的自然排序顺序存储。简而言之，这个构造函数用于将 SortedSet 对象转换为 TreeSet 对象。

**语法:**如果我们希望创建一个名为 ts 的树集，那么，它可以如下创建:

```java
TreeSet t = new TreeSet(SortedSet s);
```

**TreeSet 类中的方法在下面以表格形式描述**，稍后我们将在实现部分实现以展示。

TreeSet 实现 [SortedSet](https://www.geeksforgeeks.org/sortedset-java-examples/) 所以它拥有 Collection、 [Set](https://www.geeksforgeeks.org/set-in-java/) 、 [SortedSet 接口](https://www.geeksforgeeks.org/sortedset-java-examples/)中所有方法的可用性。以下是 Treeset 接口中的方法。下表中的“？”表示该方法适用于任何类型的对象，包括用户定义的对象。

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| [**添加(对象 o)**](https://www.geeksforgeeks.org/treeset-add-method-in-java/) | 该方法将根据在创建 TreeSet 期间提到的相同排序顺序添加指定的元素。不会添加重复条目。 |
| [**addAll(集合 c)**](https://www.geeksforgeeks.org/treeset-addall-method-in-java/) | 此方法会将指定集合的所有元素添加到集合中。集合中的元素应该是同构的，否则将引发 ClassCastException。集合的重复条目不会添加到树集中。 |
| [**天花板？**](https://www.geeksforgeeks.org/treeset-ceiling-method-in-java-with-examples/) | 此方法返回该集合中大于或等于给定元素的最少元素，如果没有这样的元素，则返回 null。 |
| [**晴()**](https://www.geeksforgeeks.org/treeset-clear-method-in-java/) | 此方法将移除所有元素。 |
| [**克隆()**](https://www.geeksforgeeks.org/treeset-clone-method-in-java/) | 方法用于返回集合的浅层副本，它只是一个简单的复制集合。 |
| [**比较器比较器()**](https://www.geeksforgeeks.org/treeset-comparator-method-in-java/) | 此方法将返回用于对 TreeSet 中的元素进行排序的比较器，或者如果使用默认的自然排序顺序，它将返回 null。 |
| [**包含(对象 o)**](https://www.geeksforgeeks.org/treeset-contains-method-in-java/) | 如果给定元素出现在 TreeSet 中，此方法将返回 true，否则将返回 false。 |
| [**下降畸胎？()**](https://www.geeksforgeeks.org/treeset-descendingiterator-method-in-java-with-examples/) | 这个方法以降序返回这个集合中元素的迭代器。 |
| [**下降集？()**](https://www.geeksforgeeks.org/treeset-descendingset-method-in-java-with-examples/) | 此方法返回此集合中包含的元素的逆序视图。 |
| [**第()**](https://www.geeksforgeeks.org/treeset-first-method-in-java/) | 如果 TreeSet 不为 null，此方法将返回 TreeSet 中的第一个元素，否则它将引发 NoSuchElementException。 |
| [**楼？**](https://www.geeksforgeeks.org/treeset-floor-method-in-java-with-examples/) | 此方法返回该集合中小于或等于给定元素的最大元素，如果没有这样的元素，则返回 null。 |
| [**【耳机(物体对元件)**](https://www.geeksforgeeks.org/treeset-headset-method-in-java/) | 此方法将返回小于指定元素的 TreeSet 元素。 |
| [**更高？**](https://www.geeksforgeeks.org/treeset-higher-method-in-java-with-examples/) | 此方法返回该集合中严格大于给定元素的最少元素，如果没有这样的元素，则返回 null。 |
| [**【isempty()**](https://www.geeksforgeeks.org/treeset-isempty-method-in-java/) | 如果此集合不包含任何元素，或者在相反的情况下为空且为假，则使用此方法返回 true。 |
| [**迭代器迭代器()**](https://www.geeksforgeeks.org/treeset-iterator-method-in-java/) | 返回一个迭代器，用于迭代集合的元素。 |
| [**最后()**](https://www.geeksforgeeks.org/treeset-last-method-in-java/) | 如果 TreeSet 不为 null，此方法将返回 TreeSet 中的最后一个元素，否则它将引发 NoSuchElementException。 |
| [**更低？**](https://www.geeksforgeeks.org/treeset-lower-method-in-java/) | 此方法返回该集合中严格小于给定元素的最大元素，如果没有这样的元素，则返回 null。 |
| [**pollFirst？()**](https://www.geeksforgeeks.org/treeset-pollfirst-method-in-java/) | 此方法检索并移除第一个(最低的)元素，如果此集合为空，则返回 null。 |
| [**花粉负荷？()**](https://www.geeksforgeeks.org/treeset-polllast-method-in-java-with-example/) | 此方法检索并移除最后一个(最高的)元素，如果此集合为空，则返回 null。 |
| [**移除(对象 o)**](https://www.geeksforgeeks.org/treeset-remove-method-in-java/) | 此方法用于从集合中返回特定元素。 |
| [**大小()**](https://www.geeksforgeeks.org/treeset-size-method-in-java/) | 此方法用于返回集合的大小或集合中存在的元素数量。 |
| **分流器()** | 此方法在此集合中的元素上创建后期绑定和故障快速拆分器。 |
| [**子集(对象从元素，对象到元素)**](https://www.geeksforgeeks.org/treeset-subset-method-in-java/) | 此方法将返回从元素到元素的元素。fromElement 是包含性的，toElement 是排他性的。 |
| [**尾集(对象来自元素)**](https://www.geeksforgeeks.org/treeset-tailset-method-in-java/) | 此方法将返回大于或等于指定元素的 TreeSet 元素。 |

</figure>

**说明:**下面的实现演示了如何创建和使用一个 TreeSet。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Illustrate Working of  TreeSet

// Importing required utility classes
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a Set interface with reference to
        // TreeSet
        Set<String> ts1 = new TreeSet<>();

        // Elements are added using add() method
        ts1.add("A");
        ts1.add("B");
        ts1.add("C");

        // Duplicates will not get insert
        ts1.add("C");

        // Elements get stored in default natural
        // Sorting Order(Ascending)
        System.out.println(ts1);
    }
}
```

**Output:** 

```java
[A, B, C]
```

**实施:**

在这里，我们将对 TreeSet 对象执行各种操作，以熟悉 java 中 TreeSet 的方法和概念。让我们看看如何在 TreeSet 上执行一些常用的操作。它们如下所示:

*   添加元素
*   访问元素
*   移除元素
*   迭代元素

现在让我们在一个干净的 java 程序的帮助下，一个接一个地讨论每个操作。

**操作 1:** 添加元素

为了给 TreeSet 添加一个元素，我们可以使用 [add()方法](https://www.geeksforgeeks.org/treeset-add-method-in-java/)。但是，插入顺序不会保留在树集中。在内部，对于每个元素，值都是按升序进行比较和排序的。我们需要注意，重复的元素是不允许的，所有重复的元素都会被忽略。此外，树集合不接受空值。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to Illustrate Addition of Elements to TreeSet

// Importing utility classes
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a Set interface with
        // reference to TreeSet class
        // Declaring object of string type
        Set<String> ts = new TreeSet<>();

        // Elements are added using add() method
        ts.add("Geek");
        ts.add("For");
        ts.add("Geeks");

        // Print all elements inside object
        System.out.println(ts);
    }
}
```

**Output:** 

```java
[For, Geek, Geeks]
```

**操作 2:** 访问元素

添加元素后，如果我们想访问元素，可以使用内置的方法，如 [contains()](https://www.geeksforgeeks.org/treeset-contains-method-in-java/) 、 [first()](https://www.geeksforgeeks.org/treeset-first-method-in-java/) 、 [last()](https://www.geeksforgeeks.org/treeset-last-method-in-java/) 等。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to Illustrate Working of TreeSet by
// Accessing the Element of TreeSet

// Importing utility classes
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a NavigableSet object  with
      // reference to TreeSet class
        NavigableSet<String> ts = new TreeSet<>();

        // Elements are added using add() method
        ts.add("Geek");
        ts.add("For");
        ts.add("Geeks");

         // Printing the elements inside the TreeSet object
        System.out.println("Tree Set is " + ts);

        String check = "Geeks";

        // Check if the above string exists in
        // the treeset or not
        System.out.println("Contains " + check + " "
                           + ts.contains(check));

        // Print the first element in
        // the TreeSet
        System.out.println("First Value " + ts.first());

        // Print the last element in
        // the TreeSet
        System.out.println("Last Value " + ts.last());

        String val = "Geek";

        // Find the values just greater
        // and smaller than the above string
        System.out.println("Higher " + ts.higher(val));
        System.out.println("Lower " + ts.lower(val));
    }
}
```

**Output:** 

```java
Tree Set is [For, Geek, Geeks]
Contains Geeks true
First Value For
Last Value Geeks
Higher Geeks
Lower For
```

**操作 3:** 移除值

可以使用 [remove()](https://www.geeksforgeeks.org/treeset-remove-method-in-java/) 方法从树集中删除这些值。还有各种其他方法用于移除第一个值或最后一个值。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate Removal of Elements
// in a TreeSet

// Importing utility classes
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of NavigableSet
        // with reference to TreeSet class
        // Declaring object of string type
        NavigableSet<String> ts = new TreeSet<>();

        // Elements are added
        // using add() method
        ts.add("Geek");
        ts.add("For");
        ts.add("Geeks");
        ts.add("A");
        ts.add("B");
        ts.add("Z");

        // Print and display initial elements of TreeSet
        System.out.println("Initial TreeSet " + ts);

        // Removing a specific existing element inserted
        // above
        ts.remove("B");

        // Printing the updated TreeSet
        System.out.println("After removing element " + ts);

        // Now removing the first element
        // using pollFirst() method
        ts.pollFirst();

        // Again printing the updated TreeSet
        System.out.println("After removing first " + ts);

        // Removing the last element
        // using pollLast() method
        ts.pollLast();

        // Lastly printing the elements of TreeSet remaining
        // to figure out pollLast() method
        System.out.println("After removing last " + ts);
    }
}
```

**Output:** 

```java
Initial TreeSet [A, B, For, Geek, Geeks, Z]
After removing element [A, For, Geek, Geeks, Z]
After removing first [For, Geek, Geeks, Z]
After removing last [For, Geek, Geeks]
```

**操作 4:** [**遍历树集**](https://www.geeksforgeeks.org/how-to-loop-over-treeset-in-java/)

有多种方法可以迭代遍历 TreeSet。最著名的是使用[增强为循环](https://www.geeksforgeeks.org/loops-in-java/)。极客们，当你在 TreeSet 上练习问题时，你会用这种方法迭代元素，因为这是树、地图和图形问题中最常用的方法。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate Working of TreeSet

// Importing utility classes
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of Set with reference to
        // TreeSet class

        // Note: You can refer above media if geek
        // is confused in programs why we are not
        // directly creating TreeSet object
        Set<String> ts = new TreeSet<>();

        // Adding elements in above object
        // using add() method
        ts.add("Geek");
        ts.add("For");
        ts.add("Geeks");
        ts.add("A");
        ts.add("B");
        ts.add("Z");

        // Now we will be using for each loop in order
        // to iterate through the TreeSet
        for (String value : ts)

            // Printing the values inside the object
            System.out.print(value + ", ");

        System.out.println();
    }
}
```

**Output:** 

```java
A, B, For, Geek, Geeks, Z,
```

### 树集的特征:

1.  TreeSet 实现 [SortedSet](https://www.geeksforgeeks.org/sortedset-java-examples/) 界面。因此，不允许重复值。
2.  树集中的对象以排序和升序存储。
3.  TreeSet 不保留元素的插入顺序，但元素按键排序。
4.  如果我们依赖于默认的自然排序顺序，那么插入到树中的对象应该是同类的和可比较的。TreeSet 不允许插入异构对象。如果我们试图添加异构对象，它会在运行时抛出 [classCastException](https://www.geeksforgeeks.org/built-exceptions-java-examples/) 。
5.  TreeSet 只能接受可比较的泛型类型。
    例如，StringBuffer 类实现了 Comparable 接口

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate What if Heterogeneous
// Objects are Inserted

// Importing all utilit classes
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Object creation
        Set<StringBuffer> ts = new TreeSet<>();

        // Adding elements to above object
        // using add() method
        ts.add(new StringBuffer("A"));
        ts.add(new StringBuffer("Z"));
        ts.add(new StringBuffer("L"));
        ts.add(new StringBuffer("B"));
        ts.add(new StringBuffer("O"));
        ts.add(new StringBuffer(1));

        // Note: StringBuffer implements Comparable
        // interface

        // Printing the elements
        System.out.println(ts);
    }
}
```

**Output**

```java
[, A, B, L, O, Z]
```