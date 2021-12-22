# Java 中的队列 offer()方法

> 原文:[https://www.geeksforgeeks.org/queue-offer-method-in-java/](https://www.geeksforgeeks.org/queue-offer-method-in-java/)

**[队列接口](https://www.geeksforgeeks.org/queue-interface-java/)** 的 **offer(E e)** 方法在不违反容量限制的情况下，将指定元素插入该队列。该方法优于 *add()* 方法，因为该方法在容器容量满时不会抛出异常，因为它返回 false。

**语法:**

```
boolean offer(E e)
```

**参数:**该方法接受一个强制参数 **e** ，它是要插入到队列中的元素。

**返回:**该方法在成功插入时返回真，否则返回假。

**异常:**函数抛出四个异常，描述如下:

*   **classcastexception** : When the class of the element to be input prevents it from being added to this container.
*   [T0】 IllegalArgumentException 【T1]: When an attribute of an element prevents it from being added to the queue.
*   [T0】 null pointerexception 【T1]: When the element to be inserted is passed as null and the interface of Queue does not allow null elements.

以下程序说明了队列的提供()方法:

**程序 1:** 在**的帮助下链接锁定程序**。

```
// Java Program Demonstrate offer()
// method of Queue

import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Queue
        Queue<Integer> Q
            = new LinkedBlockingQueue<Integer>(3);

        if (Q.offer(10))
            System.out.println("The Queue is not full"
                               + " and 10 is inserted");
        else
            System.out.println("The Queue is full");

        if (Q.offer(15))
            System.out.println("The Queue is not full"
                               + " and 15 is inserted");
        else
            System.out.println("The Queue is full");

        if (Q.offer(25))
            System.out.println("The Queue is not full"
                               + " and 25 is inserted");
        else
            System.out.println("The Queue is full");

        if (Q.offer(20))
            System.out.println("The Queue is not full"
                               + " and 20 is inserted");
        else
            System.out.println("The Queue is full");

        // before removing print Queue
        System.out.println("Queue: " + Q);
    }
}
```

**输出:**

```
The Queue is not full and 10 is inserted
The Queue is not full and 15 is inserted
The Queue is not full and 25 is inserted
The Queue is full
Queue: [10, 15, 25]

```

**方案二:**在**的配合下**。

```
// Java Program Demonstrate offer()
// method of Queue

import java.util.*;
import java.util.concurrent.ConcurrentLinkedDeque;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Queue
        Queue<Integer> Q
            = new ConcurrentLinkedDeque<Integer>();

        if (Q.offer(10))
            System.out.println("The Queue is not full"
                               + " and 10 is inserted");
        else
            System.out.println("The Queue is full");

        if (Q.offer(15))
            System.out.println("The Queue is not full"
                               + " and 15 is inserted");
        else
            System.out.println("The Queue is full");

        if (Q.offer(25))
            System.out.println("The Queue is not full"
                               + " and 25 is inserted");
        else
            System.out.println("The Queue is full");

        if (Q.offer(20))
            System.out.println("The Queue is not full"
                               + " and 20 is inserted");
        else
            System.out.println("The Queue is full");

        // before removing print Queue
        System.out.println("Queue: " + Q);
    }
}
```

**输出:**

```
The Queue is not full and 10 is inserted
The Queue is not full and 15 is inserted
The Queue is not full and 25 is inserted
The Queue is not full and 20 is inserted
Queue: [10, 15, 25, 20]

```

**节目 3:** 借助 **ArrayDeque** 。

```
// Java Program Demonstrate offer()
// method of Queue

import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Queue
        Queue<Integer> Q
            = new ArrayDeque<Integer>(6);

        if (Q.offer(10))
            System.out.println("The Queue is not full"
                               + " and 10 is inserted");
        else
            System.out.println("The Queue is full");

        if (Q.offer(15))
            System.out.println("The Queue is not full"
                               + " and 15 is inserted");
        else
            System.out.println("The Queue is full");

        if (Q.offer(25))
            System.out.println("The Queue is not full"
                               + " and 25 is inserted");
        else
            System.out.println("The Queue is full");

        if (Q.offer(20))
            System.out.println("The Queue is not full"
                               + " and 20 is inserted");
        else
            System.out.println("The Queue is full");

        // before removing print Queue
        System.out.println("Queue: " + Q);
    }
}
```

**输出:**

```
The Queue is not full and 10 is inserted
The Queue is not full and 15 is inserted
The Queue is not full and 25 is inserted
The Queue is not full and 20 is inserted
Queue: [10, 15, 25, 20]

```