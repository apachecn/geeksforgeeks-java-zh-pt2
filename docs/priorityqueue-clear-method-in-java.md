# Java 中的 PriorityQueue clear()方法

> 原文:[https://www . geesforgeks . org/priorityqueue-clear-method-in-Java/](https://www.geeksforgeeks.org/priorityqueue-clear-method-in-java/)

方法用于从优先级队列中移除所有元素。使用 clear()方法只会清除队列中的所有元素，而不会删除队列。换句话说，我们可以说 clear()方法仅用于清空现有的 PriorityQueue。

**语法:**

```
Priority_Queue.clear()
```

**参数:**该方法不取任何参数

**返回值:**函数不返回值。

下面的程序说明了 Java.util.PriorityQueue.clear()方法:

**程序 1:**

```
// Java code to illustrate clear()
import java.util.PriorityQueue;

public class PriorityQueueDemo {
    public static void main(String args[])
    {
        // Creating an empty PriorityQueue
        PriorityQueue<String> queue = new PriorityQueue<String>();

        // Use add() method to add elements into the Queue
        queue.add("Welcome");
        queue.add("To");
        queue.add("Geeks");
        queue.add("4");
        queue.add("Geeks");

        // Displaying the PriorityQueue
        System.out.println("PriorityQueue: " + queue);

        // Clearing the PriorityQueue using clear() method
        queue.clear();

        // Displaying the final Queue after clearing;
        System.out.println("The final Queue: " + queue);
    }
}
```

**Output:**

```
PriorityQueue: [4, Geeks, To, Welcome, Geeks]
The final Queue: []

```

**程序 2:**

```
// Java code to illustrate clear()
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
        System.out.println("PriorityQueue: " + queue);

        // Clearing the PriorityQueue using clear() method
        queue.clear();

        // Displaying the final Queue after clearing;
        System.out.println("The final Queue: " + queue);
    }
}
```

**Output:**

```
PriorityQueue: [5, 10, 30, 20, 15]
The final Queue: []

```