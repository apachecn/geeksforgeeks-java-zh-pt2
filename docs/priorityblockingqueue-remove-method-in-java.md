# Java 中的 PriorityBlockingQueue remove()方法

> 原文:[https://www . geeksforgeeks . org/priorityblockingqueue-remove-method-in-Java/](https://www.geeksforgeeks.org/priorityblockingqueue-remove-method-in-java/)

**[优先级阻塞队列](https://www.geeksforgeeks.org/priorityblockingqueue-class-in-java/)** 的**移除(对象 o)** 方法用于从该队列中删除元素。此方法**移除作为参数传递的元素的单个实例(如果存在的话)**。
当且仅当元素被移除时返回真，否则返回假。

**语法:**

```
public boolean remove(Object o)
```

**参数:**该方法接受一个强制参数 **o** ，该参数是要从该队列中删除的元素(如果存在)。

**返回值:**如果成功移除指定元素，则该方法返回**真**。否则此方法返回**假**。

下面的程序说明了 PriorityBlockingQueue 中的 remove()方法:

**程序 1:**

```
// Java Program Demonstrate remove()
// method of PriorityBlockingQueue

import java.util.concurrent.PriorityBlockingQueue;

public class GFG {
    public static void main(String[] args)
    {

        // create object of PriorityBlockingQueue
        PriorityBlockingQueue<Integer> pbq
            = new PriorityBlockingQueue<Integer>();

        // Add element to PriorityBlockingQueue
        pbq.put(1);
        pbq.put(2);
        pbq.put(3);
        pbq.put(4);

        // print queue
        System.out.println("Queue: " + pbq);

        // remove 2
        boolean res = pbq.remove(2);
        System.out.println("\n2 removed: " + res);

        // print queue
        System.out.println("Queue:  " + pbq);

        // remove 5
        res = pbq.remove(5);
        System.out.println("\n5 removed: " + res);

        // print queue
        System.out.println("Queue:  " + pbq);
    }
}
```

**Output:**

```
Queue: [1, 2, 3, 4]

2 removed: true
Queue:  [1, 4, 3]

5 removed: false
Queue:  [1, 4, 3]

```

```
// Java Program Demonstrate remove()
// method of PriorityBlockingQueue

import java.util.concurrent.PriorityBlockingQueue;

public class GFG {
    public static void main(String[] args)
    {

        // create object of PriorityBlockingQueue
        PriorityBlockingQueue<String> pbq
            = new PriorityBlockingQueue<String>();

        // Add element to PriorityBlockingQueue
        pbq.put("Geeks");
        pbq.put("forGeeks");
        pbq.put("A Computer");
        pbq.put("Portal");

        // print queue
        System.out.println("Queue: " + pbq);

        // remove Geeks
        boolean res = pbq.remove("Geeks");
        System.out.println("\nGeeks removed: " + res);

        // print queue
        System.out.println("Queue:  " + pbq);

        // remove SandeepJain
        res = pbq.remove("SandeepJain");
        System.out.println("\nSandeepJain removed: " + res);

        // print queue
        System.out.println("Queue:  " + pbq);
    }
}
```

**Output:**

```
Queue: [A Computer, Portal, Geeks, forGeeks]

Geeks removed: true
Queue:  [A Computer, Portal, forGeeks]

SandeepJain removed: false
Queue:  [A Computer, Portal, forGeeks]

```