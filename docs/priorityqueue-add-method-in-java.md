# Java 中的 PriorityQueue add()方法

> 原文:[https://www . geesforgeks . org/priorityqueue-add-method-in-Java/](https://www.geeksforgeeks.org/priorityqueue-add-method-in-java/)

Java 中的 Java.util.PriorityQueue.add()方法用于将特定元素添加到 PriorityQueue 中。这个方法只在内部调用带有传递给它的值的 Java.util.PriorityQueue.offer()方法。所以，它的工作原理和 offer()方法完全一样。

**语法:**

```
Priority_Queue.add(Object element)
```

**参数:**参数*元素*属于优先级队列类型，是指要添加到队列中的元素。

**返回值:**如果元素成功添加到优先级队列，函数返回真。

下面的程序说明了 Java.util.PriorityQueue.add()方法:

**程序 1:** 向队列中添加字符串元素。

```
// Java code to illustrate add()
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
    }
}
```

**Output:**

```
PriorityQueue: [4, Geeks, To, Welcome, Geeks]

```

**程序 2:** 向队列中添加整数元素。

```
// Java code to illustrate add()
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
    }
}
```

**Output:**

```
PriorityQueue: [5, 10, 30, 20, 15]

```