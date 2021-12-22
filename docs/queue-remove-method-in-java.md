# Java 中的 Queue remove()方法

> 原文:[https://www.geeksforgeeks.org/queue-remove-method-in-java/](https://www.geeksforgeeks.org/queue-remove-method-in-java/)

**[队列接口](https://www.geeksforgeeks.org/queue-interface-java/)** 的 **remove()** 方法返回并移除容器前面的元素。它删除容器的头部。当队列为空时，该方法抛出*nosucheelementexception*。

**语法:**

```java
E remove()
```

**返回:**该方法返回队列的**头**。

**异常:**当队列为空时，函数抛出*nosucheelementexception*。

下面的程序说明了队列的移除()方法:

**程序一:**借助 [**链接列表**](https://www.geeksforgeeks.org/linked-list-in-java/) 。

```java
// Java Program Demonstrate remove()
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
        System.out.println("Queue's head: " + Q.remove());

        // print head and deleted the head
        System.out.println("Queue's head: " + Q.remove());
    }
}
```

**输出:**

```java
Queue: [7855642, 35658786, 5278367, 74381793]
Queue's head: 7855642
Queue's head: 35658786

```

**节目 2:** 借助 **ArrayDeque** 。

```java
// Java Program Demonstrate remove()
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
        System.out.println("Queue's head: " + Q.remove());

        // print head and deleted the head
        System.out.println("Queue's head: " + Q.remove());
    }
}
```

**输出:**

```java
Queue: [7855642, 35658786, 5278367, 74381793]
Queue's head: 7855642
Queue's head: 35658786

```

**程序 3:** 在**的帮助下链接锁定程序**。

```java
// Java Program Demonstrate remove()
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
        System.out.println("Queue's head: " + Q.remove());

        // print head and deleted the head
        System.out.println("Queue's head: " + Q.remove());
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
// Java Program Demonstrate remove()
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
        System.out.println("Queue's head: " + Q.remove());

        // print head and deleted the head
        System.out.println("Queue's head: " + Q.remove());
    }
}
```

**输出:**

```java
Queue: [7855642, 35658786, 5278367, 74381793]
Queue's head: 7855642
Queue's head: 35658786

```

下面的程序说明了这个方法抛出的**异常:**

**节目 5:** 展示**nosucheelementexception**。

```java
// Java Program Demonstrate remove()
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
        Q.add(423);
        Q.add(3432);

        // print queue
        System.out.println("Queue: " + Q);

        // print head and deletes the head
        System.out.println("Queue's head: " + Q.remove());

        // print head and deleted the head
        System.out.println("Queue's head: " + Q.remove());

        // print queue
        System.out.println("Queue: " + Q);

        try {
            // Queue is empty now hence exception
            System.out.println("Queue's head: " + Q.element());
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
Queue: [423, 3432]
Queue's head: 423
Queue's head: 3432
Queue: []
Exception: java.util.NoSuchElementException

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/queue . html # remove–](https://docs.oracle.com/javase/8/docs/api/java/util/Queue.html#remove--)