# Java 中的 PriorityBlockingQueue poll()方法

> 原文:[https://www . geeksforgeeks . org/priorityblockingqueue-poll-method-in-Java/](https://www.geeksforgeeks.org/priorityblockingqueue-poll-method-in-java/)

### 1.轮询()方法

[优先级阻塞队列](https://www.geeksforgeeks.org/priorityblockingqueue-class-in-java/) **的 **poll()** 方法从该优先级阻塞队列的头**中检索并移除元素。此方法返回它从 PriorityBlockingQueue 中移除的元素，但是当队列为空时，此方法将返回 null。

**语法:**

```
public E poll()
```

**返回:**该方法从该优先级阻塞队列的头部返回**元素**，如果该队列为空，则返回空。

下面的程序说明了优先级阻塞队列的轮询()方法:

**示例 1:** 程序演示 PriorityBlockingQueue 上的 poll()方法，以从数字列表中移除元素。

```
// Java Program Demonstrate poll()
// method of PriorityBlockingQueue

import java.util.concurrent.PriorityBlockingQueue;

public class GFG {
    public static void main(String[] args)
    {

        // define capacity of PriorityBlockingQueue
        int capacityOfQueue = 5;

        // create object of PriorityBlockingQueue
        PriorityBlockingQueue<Integer> PrioQueue
            = new PriorityBlockingQueue<Integer>(capacityOfQueue);

        // Add numbers to PriorityBlockingQueue
        PrioQueue.offer(35658786);
        PrioQueue.offer(5278367);
        PrioQueue.offer(74381793);
        PrioQueue.offer(87625142);

        // remove numbers from head using poll()
        // and print removed number
        int removedItem = PrioQueue.poll();

        // print details
        System.out.println("Removed Element: " + removedItem);
        System.out.println("Now Queue Contains:");
        System.out.println(PrioQueue.toString());
    }
}
```

**Output:**

```
Removed Element: 5278367
Now Queue Contains:
[35658786, 87625142, 74381793]

```

**示例 2:** 程序演示 poll()方法，从字符串值列表中移除 String，如果列表为空，则返回 null。

```
// Java Program Demonstrate poll()
// method of PriorityBlockingQueue

import java.util.concurrent.PriorityBlockingQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // define capacity of PriorityBlockingQueue
        int capacityOfQueue = 5;

        // create object of PriorityBlockingQueue which contains
        // name of students
        PriorityBlockingQueue<String> names
            = new PriorityBlockingQueue<String>(capacityOfQueue);

        // Add names of students of girls college
        names.offer("Joyita");
        names.offer("Priyanka");

        // remove two names from list of names
        // and print removed name
        String removedName1 = names.poll();
        String removedName2 = names.poll();

        // print details
        System.out.println("Removed Name 1: " + removedName1);
        System.out.println("Removed Name 2: " + removedName2);
        System.out.println("Now Queue Contains:");
        System.out.println(names.toString());

        // try to remove from empty PriorityBlockingQueue
        String removedName3 = names.poll();
        System.out.println("Removed Name 3: " + removedName3);
    }
}
```

**Output:**

```
Removed Name 1: Joyita
Removed Name 2: Priyanka
Now Queue Contains:
[]
Removed Name 3: null

```

### 2.轮询(长超时，时间单位单位)方法

[优先级阻塞队列](https://www.geeksforgeeks.org/priorityblockingqueue-class-in-java/) **的**轮询(长超时，时间单位单位)**方法从该优先级阻塞队列的头**中检索并移除元素。如果 PriorityBlockingQueue 为空，那么它将一直等待，直到某个元素变为可用的指定时间。等待时间和时间单位作为方法的参数给出。

**语法:**

```
public E poll(long timeout, TimeUnit unit) throws InterruptedException
```

**参数:**
该方法接受两个参数:

1.  **超时(长)**:放弃前等待的时间，单位为单位。
2.  **单位(时间单位)**:决定如何解释超时参数的时间单位。

**返回:**这个方法从这个 PriorityBlockingQueue 的头部返回元素，如果在元素可用之前指定的等待时间已经过去，则返回 null。

**异常:**该方法只抛出一个异常**中断异常**-如果在等待时被中断

以下程序说明了优先级阻塞队列的轮询(长超时，时间单位单位)方法:

**示例 1:** 对优先级阻塞队列演示轮询(长超时，时间单位单位)方法的程序，以从数字列表中删除元素。

```
// Java Program Demonstrate poll(long timeout, TimeUnit unit)
// method of PriorityBlockingQueue

import java.util.concurrent.PriorityBlockingQueue;
import java.util.concurrent.TimeUnit;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // define capacity of PriorityBlockingQueue
        int capacityOfQueue = 5;

        // create object of PriorityBlockingQueue
        PriorityBlockingQueue<Integer> PrioQueue
            = new PriorityBlockingQueue<Integer>(capacityOfQueue);

        // Add numbers to PriorityBlockingQueue
        PrioQueue.offer(35658786);
        PrioQueue.offer(5278367);

        // Try to poll  elements from PriorityBlockingQueue
        System.out.println("Removed Number: "
                           + PrioQueue.poll(10, TimeUnit.SECONDS));
        System.out.println("List Contains" + PrioQueue);

        System.out.println("Removed Number: "
                           + PrioQueue.poll(10, TimeUnit.SECONDS));
        System.out.println("List Contains" + PrioQueue);

        System.out.println("Removed Number: "
                           + PrioQueue.poll(10, TimeUnit.SECONDS));
        System.out.println("List Contains" + PrioQueue);
    }
}
```

**Output:**

```
Removed Number: 5278367
List Contains[35658786]
Removed Number: 35658786
List Contains[]
Removed Number: null
List Contains[]

```

**参考:**

*   [https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/priorityblockingqueue . html # poll–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/PriorityBlockingQueue.html#poll--)
*   [https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/priorityblockingqueue . html # poll-long-Java . util . concurrent . time unit-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/PriorityBlockingQueue.html#poll-long-java.util.concurrent.TimeUnit-)