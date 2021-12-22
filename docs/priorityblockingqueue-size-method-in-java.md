# Java 中的 PriorityBlockingQueue size()方法

> 原文:[https://www . geeksforgeeks . org/priorityblockingqueue-size-method-in-Java/](https://www.geeksforgeeks.org/priorityblockingqueue-size-method-in-java/)

**[优先级阻塞队列](https://www.geeksforgeeks.org/priorityblockingqueue-class-in-java/)** 的**大小()**方法用于**查找队列**的当前大小。它返回集合中的元素数量。如果集合包含多个整数。元素，则该方法返回整数。最大值。

**语法:**

```
public int size()
```

**返回值:**这个方法返回这个优先级阻塞队列中存在的元素数量

下面是说明优先级阻塞队列大小()方法的程序:

**程序 1:**

```
// Java program to demonstrate
// size() method

import java.util.concurrent.PriorityBlockingQueue;

public class GFG {
    public static void main(String[] args)
    {

        // create object of PriorityBlockingQueue
        PriorityBlockingQueue<String> pbq
            = new PriorityBlockingQueue<String>();

        // Add element to PriorityBlockingQueue
        pbq.put("1");
        pbq.put("2");
        pbq.put("3");
        pbq.put("4");

        // print queue
        System.out.println("Queue:  " + pbq);
        System.out.println("Queue Size:  " + pbq.size());
    }
}
```

**Output:**

```
Queue:  [1, 2, 3, 4]
Queue Size:  4

```

**程序 2:** 演示动态改变队列的大小()。

```
// Java program to demonstrate 
// size() method 

import java.util.concurrent.PriorityBlockingQueue;

public class GFG {
    public static void main(String[] args)
    {

        // create object of PriorityBlockingQueue
        PriorityBlockingQueue<String> pbq
            = new PriorityBlockingQueue<String>();

        // Add element to PriorityBlockingQueue
        pbq.put("1");
        pbq.put("2");
        pbq.put("3");
        pbq.put("4");

        // print queue
        System.out.println("Queue:  " + pbq);
        System.out.println("Queue Size:  " + pbq.size());

        // remove 2
        boolean res = pbq.remove("2");
        System.out.println("\n2 removed: " + res);

        // print queue
        System.out.println("Queue:  " + pbq);
        System.out.println("Queue Size:  " + pbq.size());

        // add  5
        pbq.put("5");

        // print queue
        System.out.println("\n5 added");
        System.out.println("Queue:  " + pbq);
        System.out.println("Queue Size:  " + pbq.size());
    }
}
```

**Output:**

```
Queue:  [1, 2, 3, 4]
Queue Size:  4

2 removed: true
Queue:  [1, 4, 3]
Queue Size:  3

5 added
Queue:  [1, 4, 3, 5]
Queue Size:  4

```