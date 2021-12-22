# Java 中的 Queue peek()方法

> 原文:[https://www.geeksforgeeks.org/queue-peek-method-in-java/](https://www.geeksforgeeks.org/queue-peek-method-in-java/)

**[队列接口](https://www.geeksforgeeks.org/queue-interface-java/)** 的 **peek()** 方法返回容器前面的元素。它不会删除容器中的元素。这个方法返回队列的头。当队列为空时，该方法不会抛出异常，而是返回 *null* 。

**语法:**

```java
E peek()
```

**返回:**该方法返回队列的**头**，当队列为空时返回 false

下面的程序说明了队列的 peek()方法:

**程序一:**借助 [**链接列表**](https://www.geeksforgeeks.org/linked-list-in-java/) 。

```java
// Java Program Demonstrate peek()
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

        // print head
        System.out.println("Queue's head: " + Q.peek());

        // print queue
        System.out.println("Queue: " + Q);
    }
}
```

**Output:**

```java
Queue: [7855642, 35658786, 5278367, 74381793]
Queue's head: 7855642
Queue: [7855642, 35658786, 5278367, 74381793]

```

**程序 2:** 演示队列为空时队列的 peek()方法

```java
// Java Program Demonstrate peek()
// method of Queue when Queue is empty

import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws IllegalStateException
    {

        // create object of Queue
        Queue<Integer> Q
            = new LinkedList<Integer>();

        // print queue
        System.out.println("Queue: " + Q);

        // print head
        System.out.println("Queue's head: " + Q.peek());
    }
}
```

**Output:**

```java
Queue: []
Queue's head: null

```

**程序 3:** 借助 **ArrayDeque** 。

```java
// Java Program Demonstrate peek()
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

        // print head
        System.out.println("Queue's head: " + Q.peek());
    }
}
```

**Output:**

```java
Queue: [7855642, 35658786, 5278367, 74381793]
Queue's head: 7855642

```

**程序 4:** 在**的帮助下链接锁定程序**。

```java
// Java Program Demonstrate peek()
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

        // print head
        System.out.println("Queue's head: " + Q.peek());
    }
}
```

**Output:**

```java
Queue: [7855642, 35658786, 5278367, 74381793]
Queue's head: 7855642

```

**程序 5:** 在**的帮助下**并发链接请求。

```java
// Java Program Demonstrate peek()
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

        // print head
        System.out.println("Queue's head: " + Q.peek());
    }
}
```

**Output:**

```java
Queue: [7855642, 35658786, 5278367, 74381793]
Queue's head: 7855642

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/queue . html # peek–](https://docs.oracle.com/javase/8/docs/api/java/util/Queue.html#peek--)