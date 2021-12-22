# Java 中的 PriorityBlockingQueue clear()方法

> 原文:[https://www . geeksforgeeks . org/priorityblockingqueue-clear-method-in-Java/](https://www.geeksforgeeks.org/priorityblockingqueue-clear-method-in-java/)

**PriorityBlockingQueue** 的 **clear()** 方法移除该队列中的所有元素。因此，当需要清除优先级阻塞队列时，可以应用此方法。

**语法:**

```java
public void clear()
```

**参数:**
该方法不取参数。

**返回:**
此方法不返回任何内容。

**异常:**
这个方法不抛出任何异常。

下面的程序演示了如何使用 clear()方法从 PriorityBlockingQueue 中移除所有元素。

**例 1:**

```java
// Java Program to Demonstrate clear() method
// of PriorityBlockingQueue.

import java.util.concurrent.PriorityBlockingQueue;

public class GFG {

    public static void main(String[] args)
    {
        // define capacity of PriorityBlockingQueue
        int capacity = 15;

        // create object of PriorityBlockingQueue
        PriorityBlockingQueue<Integer> PrioBlockingQueue
            = new PriorityBlockingQueue<Integer>(capacity);

        // add numbers
        PrioBlockingQueue.add(78758575);
        PrioBlockingQueue.add(63447688);
        PrioBlockingQueue.add(56434788);

        // print queue after add operation
        System.out.println("After Adding  Numbers:");
        System.out.println("PriorityBlockingQueue:"
                           + PrioBlockingQueue);

        // remove all the elements using clear() method
        PrioBlockingQueue.clear();

        // print queue after clear operation
        System.out.println("\nAfter clear operation:");
        System.out.println("PriorityBlockingQueue:"
                           + PrioBlockingQueue);
    }
}
```

**Output:**

```java
After Adding  Numbers:
PriorityBlockingQueue:[56434788, 78758575, 63447688]

After clear operation:
PriorityBlockingQueue:[]

```

**示例 2:** 说明包含名称列表的优先级阻塞队列的清除方法。

```java
// Java Program to Demonstrate clear() method
// of PriorityBlockingQueue.

import java.util.concurrent.PriorityBlockingQueue;

public class GFG {

    public static void main(String[] args)
    {
        // define capacity of PriorityBlockingQueue
        int capacity = 15;

        // create object of PriorityBlockingQueue
        PriorityBlockingQueue<String> PrioBlockingQueue
            = new PriorityBlockingQueue<String>(capacity);

        // add some names
        PrioBlockingQueue.add("Tandrima");
        PrioBlockingQueue.add("Argha");
        PrioBlockingQueue.add("Arka");

        // print queue after add operation
        System.out.println("List of Names:");
        System.out.println("PriorityBlockingQueue: "
                           + PrioBlockingQueue);

        // remove all the elements using clear() method
        PrioBlockingQueue.clear();

        // print queue after clear operation
        System.out.println("\nAfter clearing List of names:");
        System.out.println("PriorityBlockingQueue:"
                           + PrioBlockingQueue);
    }
}
```

**Output:**

```java
List of Names:
PriorityBlockingQueue: [Argha, Tandrima, Arka]

After clearing List of names:
PriorityBlockingQueue:[]

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/priorityblockingqueue . html # clear–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/PriorityBlockingQueue.html#clear--)