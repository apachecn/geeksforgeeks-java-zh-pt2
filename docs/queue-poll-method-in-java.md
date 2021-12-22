# Java 中的队列轮询()方法

> 原文:[https://www.geeksforgeeks.org/queue-poll-method-in-java/](https://www.geeksforgeeks.org/queue-poll-method-in-java/)

**[队列接口](https://www.geeksforgeeks.org/queue-interface-java/)** 的 **poll()** 方法返回并移除容器前端的元素。它删除容器中的元素。当队列为空时，该方法不会抛出异常，而是返回 *null* 。

**语法:**

```java
E poll()
```

**返回:**该方法返回容器前面或队列头部的**元素。当队列为空时，它返回**空值**。**

以下程序说明了队列的轮询()方法:

**程序一:**借助 [**链接列表**](https://www.geeksforgeeks.org/linked-list-in-java/) 。

```java
// Java Program Demonstrate poll()
// method of Queue

import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Queue
        Queue<Integer> Q
            = new LinkedList<Integer>();

        // Add numbers to end of Queue
        Q.add(7855642);
        Q.add(35658786);
        Q.add(5278367);
        Q.add(74381793);

        // print queue
        System.out.println("Queue: " + Q);

        // print head and deletes the head
        System.out.println("Queue's head: " + Q.poll());

        // print head and deleted the head
        System.out.println("Queue's head: " + Q.poll());
    }
}
```

**输出:**

```java
Queue: [7855642, 35658786, 5278367, 74381793]
Queue's head: 7855642
Queue's head: 35658786

```

**程序 2:** 演示队列变空时队列的轮询()方法

```java
// Java Program Demonstrate poll()
// method of Queue when the Queue becomes empty

import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Queue
        Queue<Integer> Q
            = new LinkedList<Integer>();

        // Add numbers to end of Queue
        Q.add(423);
        Q.add(3432);

        // print queue
        System.out.println("Queue: " + Q);

        // print head and deletes the head
        System.out.println("Queue's head: " + Q.poll());

        // print head and deleted the head
        System.out.println("Queue's head: " + Q.poll());

        // print queue
        System.out.println("Queue: " + Q);

        // print null as Queue is empty now
        System.out.println("Queue's head: " + Q.poll());
    }
}
```

**输出:**

```java
Queue: [423, 3432]
Queue's head: 423
Queue's head: 3432
Queue: []
Queue's head: null

```

**节目 3:** 借助 **ArrayDeque** 。

```java
// Java Program Demonstrate poll()
// method of Queue

import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Queue
        Queue<Integer> Q
            = new ArrayDeque<Integer>();

        // Add numbers to end of Queue
        Q.add(7855642);
        Q.add(35658786);
        Q.add(5278367);
        Q.add(74381793);

        // print queue
        System.out.println("Queue: " + Q);

        // print head and deletes the head
        System.out.println("Queue's head: " + Q.poll());

        // print head and deleted the head
        System.out.println("Queue's head: " + Q.poll());
    }
}
```

**输出:**

```java
Queue: [7855642, 35658786, 5278367, 74381793]
Queue's head: 7855642
Queue's head: 35658786

```

**程序 4:** 在**的配合下**。

```java
// Java Program Demonstrate poll()
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

        // Add numbers to end of Queue
        Q.add(7855642);
        Q.add(35658786);
        Q.add(5278367);
        Q.add(74381793);

        // print queue
        System.out.println("Queue: " + Q);

        // print head and deletes the head
        System.out.println("Queue's head: " + Q.poll());

        // print head and deleted the head
        System.out.println("Queue's head: " + Q.poll());
    }
}
```

**输出:**

```java
Queue: [7855642, 35658786, 5278367, 74381793]
Queue's head: 7855642
Queue's head: 35658786

```

**项目 5:** 在**的帮助下，链接锁定了**。

```java
// Java Program Demonstrate poll()
// method of Queue

import java.util.*;
import java.util.concurrent.LinkedBlockingDeque;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Queue
        Queue<Integer> Q
            = new LinkedBlockingDeque<Integer>();

        // Add numbers to end of Queue
        Q.add(7855642);
        Q.add(35658786);
        Q.add(5278367);
        Q.add(74381793);

        // print queue
        System.out.println("Queue: " + Q);

        // print head and deletes the head
        System.out.println("Queue's head: " + Q.poll());

        // print head and deleted the head
        System.out.println("Queue's head: " + Q.poll());
    }
}
```

**输出:**

```java
Queue: [7855642, 35658786, 5278367, 74381793]
Queue's head: 7855642
Queue's head: 35658786

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/queue . html # poll–](https://docs.oracle.com/javase/8/docs/api/java/util/Queue.html#poll--)