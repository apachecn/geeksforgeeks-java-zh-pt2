# Java 中的 PriorityQueue size()方法

> 原文:[https://www . geeksforgeeks . org/priorityqueue-size-method-in-Java/](https://www.geeksforgeeks.org/priorityqueue-size-method-in-java/)

Java.util.PriorityQueue.size()方法用于获取 PriorityQueue 的大小或 PriorityQueue 中存在的元素数量。

**语法:**

```java
Priority_Queue.size()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回优先级队列中元素的大小或数量。

下面的程序说明了 Java.util.PriorityQueue.size()方法:
**程序 1:**

```java
// Java code to illustrate size()
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
        System.out.println("PriorityQueue: " + queue);

        // Displaying the size of the PriorityQueue
        System.out.println("The size of the queue is: " + queue.size());
    }
}
```

**Output:**

```java
PriorityQueue: [For, Geeks, To, Welcome, Geeks]
The size of the queue is: 5

```

**程序 2:**

```java
// Java code to illustrate size()
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
        queue.add(18);

        // Displaying the PriorityQueue
        System.out.println("PriorityQueue: " + queue);

        // Displaying the size of the PriorityQueue
        System.out.println("The size of the queue is: " + queue.size());
    }
}
```

**Output:**

```java
PriorityQueue: [5, 10, 18, 20, 15, 30]
The size of the queue is: 6

```