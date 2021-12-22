# Java 中的 TreeSet

> 原文:[https://www.geeksforgeeks.org/treeset-in-java/](https://www.geeksforgeeks.org/treeset-in-java/)

TreeSet 提供了 SortedSet 接口的实现，SortedSet 扩展了 Set 接口。它的行为类似于简单集合，只是它以排序格式存储元素。以下是 TreeSet 的特性。

*   TreeSet 使用树形数据结构进行存储。
*   对象以排序的升序存储。但是我们可以使用方法 TreeSet.descendingIterator()以降序进行迭代。
*   访问和检索时间非常快，这使得 TreeSet 成为以排序格式存储大量数据的绝佳选择。
*   TreeSet 不使用 hashCode()和 equals()方法来比较它的元素。它使用 compare()(或 compareTo())方法来确定两个元素的相等性。

**树集类的重要方法:**

*   **布尔 add(E e):** 如果指定的元素还不存在，这个方法会将它添加到这个集合中。
*   **E 上限(E e):** 此方法返回该集合中大于或等于给定元素的最少元素，如果没有这样的元素，则返回 null。
*   **布尔包含(对象 o):** 如果该集合包含指定的元素，则该方法返回真。
*   **E floor(E e):** 此方法返回该集合中小于或等于给定元素的最大元素，如果没有这样的元素，则返回 null。
*   **E pollsfirst():**此方法检索并移除第一个(最低的)元素，如果此集合为空，则返回 null。
*   **E pollLast():** 此方法检索并移除最后一个(最高的)元素，如果此集合为空，则返回 null。
*   **布尔移除(对象 o):** 该方法从该集合中移除指定的元素(如果存在)。

下面是一个非常简单的 TreeSet 实现，包括 TreeSet 正在排序，在 TreeSet 中迭代，检索第一个和最后一个元素，并删除一个元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate working TreeSet collection
import java.util.Iterator;
import java.util.TreeSet;

public class TreeSetExample
{
    public static void main(String[] args)
    {
        TreeSet<Integer> ts = new TreeSet<Integer>();
        ts.add(10);
        ts.add(61);
        ts.add(87);
        ts.add(39);

        Iterator<Integer> iterator = ts.iterator();
        System.out.print("Tree set data: ");

        // note that 87 being largest element, appears in
        // the last.
        while (iterator.hasNext())
            System.out.print(iterator.next() + " ");
        System.out.println();

        // to check if treeset is empty or not.
        if (ts.isEmpty())
            System.out.print("Tree Set is empty.");
        else
            System.out.println("Tree Set size: " + ts.size());

        // To get the smallest element from the set
        System.out.println("First data: " + ts.first());

        // To get the largest value from set
        System.out.println("Last data: " + ts.last());

        // remove 61 from set.
        if (ts.remove(61))
            System.out.println("Data is removed from tree set");
        else
            System.out.println("Data doesn't exist!");

        System.out.print("Now the tree set contain: ");
        iterator = ts.iterator();

        // Displaying the Tree set data
        while (iterator.hasNext())
            System.out.print(iterator.next() + " ");

        System.out.println();
        System.out.println("Now the size of tree set: " +
                           ts.size());

        // Remove all
        ts.clear();
        if (ts.isEmpty())
            System.out.print("Tree Set is empty.");
        else
            System.out.println("Tree Set size: " + ts.size());
    }
}
```

**输出:**

```
Tree set data: 10 39 61 87 

Tree Set size: 4

First data: 10

Last data: 87

Data is removed from tree set

Now the tree set contain: 10 39 87 

Now the size of tree set: 3

Tree Set is empty.
```

更多详情请参考 Java 中的 [**TreeSet，并附带示例**](https://www.geeksforgeeks.org/treeset-class-java-examples/) 。

本文由**里沙布·马赫塞供稿。**如果发现有不正确的地方，请写评论，或者想分享更多关于上面讨论的话题的信息