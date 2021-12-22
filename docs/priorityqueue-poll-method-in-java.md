# Java 中的优先级队列轮询()方法

> 原文:[https://www . geesforgeks . org/priorityqueue-poll-method-in-Java/](https://www.geeksforgeeks.org/priorityqueue-poll-method-in-java/)

java 中的 java.util.PriorityQueue.poll()方法用于检索或获取并移除 Queue 的第一个元素或位于 Queue 头部的元素。 [peek()](https://www.geeksforgeeks.org/priorityqueue-peek-method-in-java/) 方法只检索头部的元素，但是 poll()也会在检索的同时删除该元素。如果队列为空，则返回空。

**语法:**

```
Priority_Queue.poll()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回队列头部的元素，否则如果队列为空，则返回空。

下面的程序说明了 java.util.PriorityQueue.poll()方法的使用:
**程序 1:**

```
// Java code to illustrate poll()
import java.util.*;

public class PriorityQueueDemo {
    public static void main(String args[])
    {
        // Creating an empty PriorityQueue
        PriorityQueue<String> queue = new PriorityQueue<String>();

        // Use add() method to add elements into the Queue
        queue.add("Welcome");
        queue.add("To");
        queue.add("Geeks");
        queue.add("For");
        queue.add("Geeks");

        // Displaying the PriorityQueue
        System.out.println("Initial PriorityQueue: " + queue);

        // Fetching and removing the element at the head of the queue
        System.out.println("The element at the head of the"
                           + " queue is: " + queue.poll());

        // Displaying the Queue after the Operation
        System.out.println("Final PriorityQueue: " + queue);
    }
}
```

**Output:**

```
Initial PriorityQueue: [For, Geeks, To, Welcome, Geeks]
The element at the head of the queue is: For
Final PriorityQueue: [Geeks, Geeks, To, Welcome]

```

**程序 2:**

```
// Java code to illustrate poll()
import java.util.*;

public class PriorityQueueDemo {
    public static void main(String args[])
    {
        // Creating an empty PriorityQueue
        PriorityQueue<Integer> queue = new PriorityQueue<Integer>();

        // Use add() method to add elements into the Queue
        queue.add(10);
        queue.add(15);
        queue.add(30);
        queue.add(20);
        queue.add(5);

        // Displaying the PriorityQueue
        System.out.println("Initial PriorityQueue: " + queue);

        // Fetching the element at the head of the queue
        System.out.println("The element at the head of the"
                           + " queue is: " + queue.poll());

        // Displaying the Queue after the Operation
        System.out.println("Final PriorityQueue: " + queue);
    }
}
```

**Output:**

```
Initial PriorityQueue: [5, 10, 30, 20, 15]
The element at the head of the queue is: 5
Final PriorityQueue: [10, 15, 30, 20]

```