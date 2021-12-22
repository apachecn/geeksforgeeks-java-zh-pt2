# Java 中的 PriorityQueue offer()方法

> 原文:[https://www . geesforgeks . org/priorityqueue-offer-method-in-Java/](https://www.geeksforgeeks.org/priorityqueue-offer-method-in-java/)

java.util.PriorityQueue.offer()方法用于将特定元素插入优先级队列。它的作用类似于优先级队列的 [add()](https://www.geeksforgeeks.org/priorityqueue-add-method-in-java/) 方法。

**语法:**

```java
Priority_Queue.offer(Object element)
```

**参数:**参数*元素*属于优先级队列类型，指的是要插入队列的元素。

**返回值:**如果该值成功插入队列，则该方法返回真。

**异常:**方法可以抛出两种类型的异常:

*   空指针异常:如果要插入的元素为空。
*   ClassCastException:如果要插入的元素属于不同的类型，无法与队列的现有元素进行比较。

下面的程序说明了 java.util.PriorityQueue.offer()方法
**程序 1:**

```java
// Java code to illustrate offer()
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
        queue.add("4");
        queue.add("Geeks");

        // Displaying the PriorityQueue
        System.out.println("Initial PriorityQueue: " + queue);

        // Inserting using offer()
        queue.offer("The");
        queue.offer("Priority");
        queue.offer("Class");

        // Displaying th final Queue
        System.out.println("Priority queue after Insertion: " + queue);
    }
}
```

**Output:**

```java
Initial PriorityQueue: [4, Geeks, To, Welcome, Geeks]
Priority queue after Insertion: [4, Class, Priority, Geeks, Geeks, To, The, Welcome]

```

**程序 2:**

```java
// Java code to illustrate offer()
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

        // Inserting using offer()
        queue.offer(100);
        queue.offer(120);
        queue.offer(150);

        // Displaying th final Queue
        System.out.println("Priority queue after Insertion: " + queue);
    }
}
```

**Output:**

```java
Initial PriorityQueue: [5, 10, 30, 20, 15]
Priority queue after Insertion: [5, 10, 30, 20, 15, 100, 120, 150]

```