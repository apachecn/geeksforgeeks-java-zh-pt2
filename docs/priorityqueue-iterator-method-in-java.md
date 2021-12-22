# Java 中的 PriorityQueue 迭代器()方法

> 原文:[https://www . geeksforgeeks . org/priorityqueue-iterator-method-in-Java/](https://www.geeksforgeeks.org/priorityqueue-iterator-method-in-java/)

Java . util . priorityqueue . iterator()方法用于返回与优先级队列相同元素的迭代器。元素从队列中随机返回。

**语法:**

```
Iterator *iterate_value* = Priority_Queue.iterator();

```

**参数:**函数不取任何参数。

**返回值:**方法迭代队列的元素并返回值(迭代器)。

下面的程序说明了 Java . util . priority queue . iterator()方法:
**程序 1:**

```
// Java code to illustrate iterator()
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
        System.out.println("PriorityQueue: " + queue);

        // Creating an iterator
        Iterator value = queue.iterator();

        // Displaying the values after iterating through the queue
        System.out.println("The iterator values are: ");
        while (value.hasNext()) {
            System.out.println(value.next());
        }
    }
}
```

**Output:**

```
PriorityQueue: [4, Geeks, To, Welcome, Geeks]
The iterator values are: 
4
Geeks
To
Welcome
Geeks

```

**程序 2:**

```
// Java code to illustrate iterator()
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

        // Creating an iterator
        Iterator value = queue.iterator();

        // Displaying the values after iterating through the queue
        System.out.println("The iterator values are: ");
        while (value.hasNext()) {
            System.out.println(value.next());
        }
    }
}
```

**Output:**

```
PriorityQueue: [5, 10, 30, 20, 15]
The iterator values are: 
5
10
30
20
15

```