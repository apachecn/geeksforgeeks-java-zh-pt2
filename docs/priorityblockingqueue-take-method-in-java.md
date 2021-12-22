# Java 中的 PriorityBlockingQueue take()方法

> 原文:[https://www . geeksforgeeks . org/priorityblockingqueue-take-method-in-Java/](https://www.geeksforgeeks.org/priorityblockingqueue-take-method-in-java/)

**[优先级阻塞队列](https://www.geeksforgeeks.org/priorityblockingqueue-class-in-java/)** 的 **take()** 方法移除后返回队列头。如果队列为空，则此方法将等待直到某个元素变得可用。

**语法:**

```
public E take() throws InterruptedException
```

**返回:**该方法返回该优先级阻塞队列的**头**的值。

**异常:**如果在等待元素可用时被中断，该方法将引发**中断异常**。

下面的程序说明了优先阻塞队列的 take()方法:

**示例 1:** 演示包含数字列表的 PriorityBlockingQueue 上的 take()方法。

```
// Java Program Demonstrate take()
// method of PriorityBlockingQueue

import java.util.concurrent.PriorityBlockingQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of PriorityBlockingQueue
        PriorityBlockingQueue<Integer> PrioQueue
            = new PriorityBlockingQueue<Integer>();

        // Add numbers to PriorityBlockingQueue
        PrioQueue.put(7855642);
        PrioQueue.put(35658786);
        PrioQueue.put(5278367);
        PrioQueue.put(74381793);

        // before removing print queue
        System.out.println("Queue: " + PrioQueue);

        // Apply take() method
        int head = PrioQueue.take();

        // Print head of queue using take() method
        System.out.println("Head of PriorityBlockingQueue"
                           + " using take(): " + head);

        System.out.print("After removing head, Queue: "
                         + PrioQueue);
    }
}
```

**输出:**

```
Queue: [5278367, 35658786, 7855642, 74381793]
Head of PriorityBlockingQueue using take(): 5278367
After removing head, Queue: [7855642, 35658786, 74381793]

```

**示例 2:** 演示包含字符串

```
// Java Program Demonstrate take()
// method of PriorityBlockingQueue

import java.util.concurrent.PriorityBlockingQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of PriorityBlockingQueue
        // which contains Strings
        PriorityBlockingQueue<String> names
            = new PriorityBlockingQueue<String>();

        // Add string
        names.add("Geeks");
        names.add("forGeeks");
        names.add("A computer portal");

        // print list of names
        System.out.println(names);

        // Apply take() method
        String head = names.take();

        // Print head of queue using take() method
        System.out.println("Head of Queue: "
                           + head);
        System.out.print("After removing head, Queue: "
                         + names);
    }
}
```

**的优先级阻塞队列的 take()方法输出:**

```
[A computer portal, forGeeks, Geeks]
Head of Queue: A computer portal
After removing head, Queue: [Geeks, forGeeks]

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/priorityblockingqueue . html # take–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/PriorityBlockingQueue.html#take--)