# Java 中的优先级队列

> 原文:[https://www.geeksforgeeks.org/priority-queue-class-in-java/](https://www.geeksforgeeks.org/priority-queue-class-in-java/)

当应该根据优先级处理对象时，使用优先级队列。众所周知，一个[队列](https://www.geeksforgeeks.org/queue-interface-java/)遵循先进先出算法，但有时队列的元素需要根据优先级进行处理，也就是优先级队列开始发挥作用的时候。优先级队列基于优先级堆。优先级队列的元素根据自然顺序进行排序，或者由队列构建时提供的比较器进行排序，具体取决于使用的构造函数。

![Queue-Deque-PriorityQueue-In-Java](img/60cee2c4d09185f472d67be6d39b42a1.png)

在下面的优先级队列中，具有最大 ASCII 值的元素将具有最高优先级。

![Working of PriorityQueue](img/2d7eae19bb8d844400e2d53a8b065bf5.png)

**申报:**

```
public class PriorityQueue<E> extends AbstractQueue<E> implements Serializable

where E is the type of elements held in this queue

```

该类实现了**可序列化**、**可迭代< E >** 、**集合<E>T5】、[队列<E>T7】接口。](https://www.geeksforgeeks.org/queue-interface-java/)**

优先级队列上的几个**要点如下:**

*   优先级队列不允许为空。
*   我们不能创建不可比较对象的优先级队列
*   优先级队列是未绑定的队列。
*   相对于指定的顺序，这个队列的头是最少的元素。如果多个元素以最小的价值捆绑在一起，头部就是这些元素中的一个——捆绑是任意断开的。
*   由于 PriorityQueue 不是线程安全的，所以 java 提供了 [PriorityBlockingQueue](https://www.geeksforgeeks.org/priorityblockingqueue-class-in-java/#:~:text=PriorityBlockingQueue%20is%20an%20unbounded%20blocking,and%20supplies%20blocking%20retrieval%20operations.&text=PriorityBlockingQueue%20class%20and%20its%20iterator,the%20Collection%20and%20Iterator%20interfaces.) 类，该类实现了在 java 多线程环境中使用的 [BlockingQueue](https://www.geeksforgeeks.org/blockingqueue-interface-in-java/#:~:text=Methods%20in%20Blocking%20Queue%20Interface&text=Removes%20all%20available%20elements%20from,them%20to%20the%20given%20collection.&text=Removes%20at%20most%20the%20given,them%20to%20the%20given%20collection.) 接口。
*   队列检索操作轮询、移除、查看和元素访问队列头部的元素。
*   它为添加和轮询方法提供了 O(log(n))时间。
*   它继承了**抽象队列**、**抽象集合**、**集合**和**对象**类的方法。

**施工人员:**

**1。PriorityQueue():** 创建一个具有默认初始容量(11)的 PriorityQueue，它根据元素的自然顺序对其进行排序。

> 优先级队列 <e>pq =新优先级队列<e>()；</e></e>

**2。优先级队列(集合< E > c):** 创建包含指定集合中元素的优先级队列。

> 优先权队列 <e>pq =新优先权队列<e>(集合<e>【c】；</e></e></e>

**3。优先级队列(int initialCapacity)** :创建一个具有指定初始容量的优先级队列，该队列根据元素的自然顺序对其进行排序。

> 优先级队列 <e>pq =新优先级队列 <e>(int 初始容量)；</e></e>

**4。优先级队列(int initialCapacity，Comparator<E>Comparator):**创建具有指定初始容量的优先级队列，该队列根据指定的比较器对其元素进行排序。

> 优先级队列 <e>pq =新优先级队列(int initialCapacity，Comparator<e>Comparator)；</e></e>

**5。优先级队列(优先级队列< E > c)** :创建一个包含指定优先级队列中元素的优先级队列。

> PriorityQueue <e>pq =新 priority queue(priority queue<e>c)；</e></e>

**6。优先级队列(排序集< E > c)** :创建一个包含指定排序集中元素的优先级队列。

> priority queue<e>【pq =新优先级队列】<e>(sort dset<e>【c】；</e></e></e>

**示例:**

下面的例子解释了优先级队列的以下基本操作。

*   [布尔 add(E 元素):](https://www.geeksforgeeks.org/priorityqueue-add-method-in-java/)这个方法将指定的元素插入到这个优先级队列中。
*   [public peek():](https://www.geeksforgeeks.org/queue-peek-method-in-java/) 此方法检索但不移除此队列的头，如果此队列为空，则返回 null。
*   [public poll():](https://www.geeksforgeeks.org/queue-poll-method-in-java/) 此方法检索并删除此队列的头，如果此队列为空，则返回 null。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the
// working of PriorityQueue
import java.util.*;

class PriorityQueueDemo {

      // Main Method
    public static void main(String args[])
    {
        // Creating empty priority queue
        PriorityQueue<Integer> pQueue = new PriorityQueue<Integer>();

        // Adding items to the pQueue using add()
        pQueue.add(10);
        pQueue.add(20);
        pQueue.add(15);

        // Printing the top element of PriorityQueue
        System.out.println(pQueue.peek());

        // Printing the top element and removing it
        // from the PriorityQueue container
        System.out.println(pQueue.poll());

        // Printing the top element again
        System.out.println(pQueue.peek());
    }
}
```

**输出:**

```
10
10
15

```

### **优先队列上的操作**

让我们看看如何在优先级队列类上执行一些常用的操作。

**1。添加元素:**为了在优先级队列中添加一个元素，我们可以使用 [add()](https://www.geeksforgeeks.org/priorityqueue-add-method-in-java/) 方法。插入顺序不会保留在优先级队列中。元素是根据优先级顺序存储的，默认情况下，优先级顺序是升序。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to add elements
// to a PriorityQueue
import java.util.*;
import java.io.*;

public class PriorityQueueDemo {

    public static void main(String args[])
    {
        PriorityQueue<String> pq = new PriorityQueue<>();

        pq.add("Geeks");
        pq.add("For");
        pq.add("Geeks");

        System.out.println(pq);
    }
}
```

**输出:**

```
[For, Geeks, Geeks]

```

**2。移除元素:**为了从优先级队列中移除元素，我们可以使用[移除()](https://www.geeksforgeeks.org/priorityqueue-remove-method-in-java/)方法。如果有多个这样的对象，则删除第一个出现的对象。除此之外，poll()方法也用于移除头部并将其返回。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to remove elements
// from a PriorityQueue

import java.util.*;
import java.io.*;

public class PriorityQueueDemo {

    public static void main(String args[])
    {
        PriorityQueue<String> pq = new PriorityQueue<>();

        pq.add("Geeks");
        pq.add("For");
        pq.add("Geeks");

        System.out.println("Initial PriorityQueue " + pq);

          // using the method
        pq.remove("Geeks");

        System.out.println("After Remove - " + pq);

        System.out.println("Poll Method - " + pq.poll());

        System.out.println("Final PriorityQueue - " + pq);
    }
}
```

**输出:**

```
Initial PriorityQueue [For, Geeks, Geeks]
After Remove - [For, Geeks]
Poll Method - For
Final PriorityQueue - [Geeks]

```

**3。访问元素:**由于队列遵循先进先出原则，我们只能访问队列的头部。要从优先级队列中访问元素，我们可以使用 peek()方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to access elements
// from a PriorityQueue
import java.util.*;

class PriorityQueueDemo {

      // Main Method
    public static void main(String[] args)
    {

        // Creating a priority queue
        PriorityQueue<String> pq = new PriorityQueue<>();
        pq.add("Geeks");
        pq.add("For");
        pq.add("Geeks");
        System.out.println("PriorityQueue: " + pq);

        // Using the peek() method
        String element = pq.peek();
        System.out.println("Accessed Element: " + element);
    }
}
```

**输出:**

```
PriorityQueue: [For, Geeks, Geeks]
Accessed Element: For

```

**4。迭代优先级队列:**有多种方法迭代优先级队列。最著名的方法是将队列转换为数组，并使用 for 循环遍历。然而，队列还有一个内置的迭代器，可以用来遍历队列。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to iterate elements
// to a PriorityQueue

import java.util.*;

public class PriorityQueueDemo {

      // Main Method
    public static void main(String args[])
    {
        PriorityQueue<String> pq = new PriorityQueue<>();

        pq.add("Geeks");
        pq.add("For");
        pq.add("Geeks");

        Iterator iterator = pq.iterator();

        while (iterator.hasNext()) {
            System.out.print(iterator.next() + " ");
        }
    }
}
```

**输出:**

```
For Geeks Geeks 

```

### **优先级队列类**中的方法

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| [加(E e)](https://www.geeksforgeeks.org/priorityqueue-add-method-in-java/) | 将指定的元素插入此优先级队列。 |
| [晴()](https://www.geeksforgeeks.org/priorityqueue-clear-method-in-java/#:~:text=clear()%20method%20is%20used,only%20empty%20an%20existing%20PriorityQueue.) | 从此优先级队列中移除所有元素。 |
| [比较器()](https://www.geeksforgeeks.org/priorityqueue-comparator-method-in-java/) | 返回用于对该队列中的元素进行排序的比较器，如果根据元素的自然顺序对该队列进行排序，则返回 null。 |
| [包含(对象 o)](https://www.geeksforgeeks.org/priorityqueue-contains-method-in-java/#:~:text=PriorityQueue.,any%20particular%20element%20or%20not.&text=Return%20Value%3A%20The%20method%20returns,queue%20otherwise%20it%20returns%20False.) | 如果此队列包含指定的元素，则返回 true。 |
| forEach(消费者 super E>行动) | 对 Iterable 的每个元素执行给定的操作，直到所有元素都被处理完或者该操作引发异常。 |
| [迭代器()](https://www.geeksforgeeks.org/priorityqueue-iterator-method-in-java/) | 返回该队列中元素的迭代器。 |
| [报价(E e)](https://www.geeksforgeeks.org/priorityqueue-offer-method-in-java/) | 将指定的元素插入此优先级队列。 |
| [移除(物体 o)](https://www.geeksforgeeks.org/priorityqueue-remove-method-in-java/) | 从该队列中移除指定元素的单个实例(如果存在)。 |
| 移除所有(集合> c) | 移除此集合中也包含在指定集合中的所有元素(可选操作)。 |
| 移除 If(谓词 super E>过滤器) | 移除此集合中满足给定谓词的所有元素。 |
| 零售(集合> c) | 仅保留此集合中包含在指定集合中的元素(可选操作)。 |
| [分流器()](https://www.geeksforgeeks.org/priorityqueue-spliterator-method-in-java/) | 对该队列中的元素创建后期绑定和故障快速拆分器。 |
| [toaarray()](https://www.geeksforgeeks.org/priorityqueue-toarray-method-in-java/#:~:text=toArray(arr%5B%5D)%20method%20in,the%20previous%20method%20without%20parameters.) | 返回包含该队列中所有元素的数组。 |
| [toaarray(t[]a)](https://www.geeksforgeeks.org/priorityqueue-toarray-method-in-java/#:~:text=toArray(arr%5B%5D)%20method%20in,the%20previous%20method%20without%20parameters.) | 返回包含该队列中所有元素的数组；返回数组的运行时类型是指定数组的运行时类型。 |

</figure>

### **Java . util . abstract queue 类中声明的方法**

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| [addAll(收藏<？延伸 E > c)](https://www.geeksforgeeks.org/abstractqueue-addall-method-in-java-with-examples/) | 将指定集合中的所有元素添加到该队列中。 |
| [元素()](https://www.geeksforgeeks.org/abstractqueue-element-method-in-java-with-examples/) | 检索但不移除该队列的头。 |
| [移除()](https://www.geeksforgeeks.org/abstractqueue-remove-method-in-java-with-examples/#:~:text=The%20remove()%20method%20of,the%20head%20of%20this%20queue.&text=Parameters%3A%20This%20method%20does%20not,if%20the%20queue%20is%20empty.) | 检索并删除该队列的头。 |

</figure>

### **Java . util . abstract collection 类中声明的方法**

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| [包含所有(收藏<？> c)](https://www.geeksforgeeks.org/abstractcollection-containsall-method-in-java-with-examples/) | 如果此集合包含指定集合中的所有元素，则返回 true。 |
| [【isempty()](https://www.geeksforgeeks.org/abstractcollection-isempty-method-in-java-with-examples/) | 如果此集合不包含元素，则返回 true。 |
| [toString()](https://www.geeksforgeeks.org/abstractcollection-tostring-method-in-java-with-examples/) | 返回此集合的字符串表示形式。 |

</figure>

### **接口 java.util.Collection 中声明的方法**

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| 包含所有(集合> c) | 如果此集合包含指定集合中的所有元素，则返回 true。 |
| 等于(对象 0) | 将指定的对象与此集合进行比较，看是否相等。 |
| hashCode() | 返回此集合的哈希代码值。 |
| isEmpty() | 如果此集合不包含元素，则返回 true。 |
| 并行流() | 以此集合为源返回一个可能并行的流。 |
| 大小() | 返回此集合中的元素数量。 |
| 流() | 返回以此集合为源的顺序流。 |
| toArray(IntFunction <t>生成器)</t> | 使用提供的生成器函数分配返回的数组，返回包含此集合中所有元素的数组。 |

</figure>

### **接口 java.util.Queue 中声明的方法**

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| [peek()](https://www.geeksforgeeks.org/queue-peek-method-in-java/) | 检索但不移除该队列的头，如果该队列为空，则返回 null。 |
| [投票()](https://www.geeksforgeeks.org/queue-poll-method-in-java/) | 检索并删除该队列的头，如果该队列为空，则返回 null。 |

</figure>

**应用程序**:

*   实现[迪克斯特拉的](https://www.geeksforgeeks.org/dijkstras-algorithm-for-adjacency-list-representation-greedy-algo-8/)和[普里姆的](https://www.geeksforgeeks.org/prims-algorithm-using-priority_queue-stl/)算法。
*   [K 次否定后最大化数组和](https://www.geeksforgeeks.org/maximize-array-sum-k-negations-set-2/)

**相关文章**:

*   [Java 中的 Java.util.PriorityQueue 类](https://www.geeksforgeeks.org/java-util-priorityqueue-class-java/)
*   [在 Java 中通过比较器实现优先级队列](https://www.geeksforgeeks.org/implement-priorityqueue-comparator-java/)

本文由**迈哈克·库马尔供稿。**如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。