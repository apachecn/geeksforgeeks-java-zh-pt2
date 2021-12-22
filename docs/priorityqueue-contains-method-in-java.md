# PriorityQueue 在 Java 中包含()方法

> 原文:[https://www . geesforgeks . org/priorityqueue-contains-method-in-Java/](https://www.geeksforgeeks.org/priorityqueue-contains-method-in-java/)

Java . util . PriorityQueue . contains()方法用于检查 PriorityQueue 中是否存在特定元素。所以基本上它是用来检查一个队列是否包含任何特定的元素。

**语法:**

```
Priority_Queue.contains(Object element)
```

**参数:**参数*元素*属于优先级队列类型。这是需要测试队列中是否存在的元素。

**返回值:**如果元素存在于队列中，该方法返回*真*，否则返回假。

下面的程序说明了 Java . util . priorityqueue . contains()方法:
**程序 1:**

```
// Java code to illustrate contains()
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

        // Check for "Geeks" in the queue
        System.out.println("Does the Queue contains 'Geeks'? "
        +queue.contains("Geeks"));

        // Check for "4" in the queue
        System.out.println("Does the Queue contains '4'? "
        +queue.contains("4"));

        // Check if the Queue contains "No"
        System.out.println("Does the Queue contains 'No'? "
        +queue.contains("No"));
    }
}
```

**Output:**

```
PriorityQueue: [4, Geeks, To, Welcome, Geeks]
Does the Queue contains 'Geeks'? true
Does the Queue contains '4'? true
Does the Queue contains 'No'? false

```

**程序 2:**

```
// Java code to illustrate contains()
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

        // Check for '15' in the queue
        System.out.println("Does the Queue contains '15'? "
        +queue.contains(15));

        // Check for '2' in the queue
        System.out.println("Does the Queue contains '2'? "
        +queue.contains(2));

        // Check if the Queue contains '10'
        System.out.println("Does the Queue contains '10'? "
        +queue.contains(10));
    }
}
```

**Output:**

```
PriorityQueue: [5, 10, 30, 20, 15]
Does the Queue contains '15'? true
Does the Queue contains '2'? false
Does the Queue contains '10'? true

```