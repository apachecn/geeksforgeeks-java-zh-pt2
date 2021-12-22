# Java 中的 Queue 元素()方法

> 原文:[https://www.geeksforgeeks.org/queue-element-method-in-java/](https://www.geeksforgeeks.org/queue-element-method-in-java/)

**[队列接口](https://www.geeksforgeeks.org/queue-interface-java/)** 的**元素()**方法返回容器前面的元素。它不会删除容器中的元素。这个方法返回队列的头。

此方法与 peek()的区别仅在于，如果此队列为空，它将引发异常。

**语法:**

```java
E element()
```

**返回:**该方法返回队列的**头**。

**异常:**当队列为空，函数被调用时，函数抛出*nosucheelementexception*。

下面的程序说明了队列的元素()方法:

**程序一:**借助 [**链接列表**](https://www.geeksforgeeks.org/linked-list-in-java/) 。

```java
// Java Program Demonstrate element()
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
        System.out.println("Queue's head: " + Q.element());
    }
}
```

**输出:**

```java
Queue: [7855642, 35658786, 5278367, 74381793]
Queue's head: 7855642

```

**节目 2:** 借助 **ArrayDeque** 。

```java
// Java Program Demonstrate element()
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
        System.out.println("Queue's head: " + Q.element());
    }
}
```

**输出:**

```java
Queue: [7855642, 35658786, 5278367, 74381793]
Queue's head: 7855642

```

**程序 3:** 在**的帮助下链接锁定程序**。

```java
// Java Program Demonstrate element()
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
        System.out.println("Queue's head: " + Q.element());
    }
}
```

**输出:**

```java
Queue: [7855642, 35658786, 5278367, 74381793]
Queue's head: 7855642

```

**程序 4:** 在**的配合下**。

```java
// Java Program Demonstrate element()
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
        System.out.println("Queue's head: " + Q.element());
    }
}
```

**输出:**

```java
Queue: [7855642, 35658786, 5278367, 74381793]
Queue's head: 7855642

```

下面的程序说明了这个方法抛出的**异常:**

**节目 5:** 展示**nosucheelementexception**。

```java
// Java Program Demonstrate element()
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
        System.out.println("Queue's head: " + Q.element());

        Q.clear();

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
Queue: [7855642, 35658786, 5278367, 74381793]
Queue's head: 7855642
Queue: []
Exception: java.util.NoSuchElementException

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/queue . html #元素–](https://docs.oracle.com/javase/8/docs/api/java/util/Queue.html#element--)