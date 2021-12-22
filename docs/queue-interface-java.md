# Java 中的队列接口

> 原文:[https://www.geeksforgeeks.org/queue-interface-java/](https://www.geeksforgeeks.org/queue-interface-java/)

出现在 [java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包中并扩展了[收集接口](https://www.geeksforgeeks.org/collections-in-java-2/)的队列接口用于以先进先出的顺序保存将要处理的元素。它是一个有序的对象列表，其用途仅限于在列表末尾插入元素和从列表开头删除元素(即，它遵循先进先出原则)。

![Queue-Deque-PriorityQueue-In-Java](img/60cee2c4d09185f472d67be6d39b42a1.png)

作为一个接口，队列需要一个具体的类来声明，最常见的类是 Java 中的 [PriorityQueue](https://www.geeksforgeeks.org/priority-queue-class-in-java-2/) 和 [LinkedList](https://www.geeksforgeeks.org/linked-list-in-java/) 。请注意，这两种实现都不是线程安全的。[如果需要线程安全实现，优先级阻塞队列](https://www.geeksforgeeks.org/priorityblockingqueue-class-in-java/)是一个替代实现。

**声明:**队列接口声明为:

> 公共接口队列扩展集合

**创建队列对象**
由于*队列*是[接口](https://www.geeksforgeeks.org/interfaces-in-java/)，因此不能创建队列类型的对象。我们总是需要一个扩展这个列表的类来创建一个对象。此外，在 Java 1.5 中引入[泛型](https://www.geeksforgeeks.org/generics-in-java/)后，可以限制可以存储在队列中的对象类型。这种类型安全队列可以定义为:

> // Obj 是要存储在 Queue
> Queue<Obj>Queue =新优先级 Queue<Obj>()；

**队列示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate a Queue

import java.util.LinkedList;
import java.util.Queue;

public class QueueExample {

    public static void main(String[] args)
    {
        Queue<Integer> q
            = new LinkedList<>();

        // Adds elements {0, 1, 2, 3, 4} to
        // the queue
        for (int i = 0; i < 5; i++)
            q.add(i);

        // Display contents of the queue.
        System.out.println("Elements of queue "
                           + q);

        // To remove the head of queue.
        int removedele = q.remove();
        System.out.println("removed element-"
                           + removedele);

        System.out.println(q);

        // To view the head of queue
        int head = q.peek();
        System.out.println("head of queue-"
                           + head);

        // Rest all methods of collection
        // interface like size and contains
        // can be used with this
        // implementation.
        int size = q.size();
        System.out.println("Size of queue-"
                           + size);
    }
}
```

**Output:** 

```
Elements of queue [0, 1, 2, 3, 4]
removed element-0
[1, 2, 3, 4]
head of queue-1
Size of queue-4
```

### 队列接口上的操作

让我们看看如何使用[优先级队列类](https://www.geeksforgeeks.org/priority-queue-class-in-java-2/)对队列执行一些常用的操作。
T3】1。添加元素:为了在队列中添加一个元素，我们可以使用 [add()方法](https://www.geeksforgeeks.org/queue-add-method-in-java/)。插入顺序不会保留在优先级队列中。元素是根据优先级顺序存储的，默认情况下，优先级顺序是升序。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to add elements
// to a Queue

import java.util.*;

public class GFG {

    public static void main(String args[])
    {
        Queue<String> pq = new PriorityQueue<>();

        pq.add("Geeks");
        pq.add("For");
        pq.add("Geeks");

        System.out.println(pq);
    }
}
```

**Output:** 

```
[For, Geeks, Geeks]
```