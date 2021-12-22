# Java 中的 Queue add()方法

> 原文:[https://www.geeksforgeeks.org/queue-add-method-in-java/](https://www.geeksforgeeks.org/queue-add-method-in-java/)

**[【队列接口】](https://www.geeksforgeeks.org/queue-interface-java/)** 的 **add(E e)** 方法将参数中传递的元素插入到队列的末尾，如果有空间的话。如果队列受到容量限制，没有空间可供插入，它将返回一个*illegalstatexception*。函数在成功插入时返回 true。

**语法:**

```java
boolean add(E e)
```

**参数:**该方法接受一个强制参数 **e** ，它是要插入到队列末尾的元素。

**返回:**此方法在成功插入时返回**真**。

**异常:**函数抛出四个异常，描述如下:

*   **classcastexception** : When the class of the element to be input prevents it from being added to this container.
*   [T0】 illegalsteexception 【T1]: When the capacity of the container is full and the insertion is completed.
*   [T0】 IllegalArgumentException 【T1]: When an attribute of an element prevents it from being added to the queue.
*   [T0】 NullPointerException 【T1]: When the element to be inserted is passed as null and the interface of Queue does not allow null elements.

下面的程序说明了队列的 add()方法:

**程序一:**借助 [**链接列表**](https://www.geeksforgeeks.org/linked-list-in-java/) 。

```java
// Java Program Demonstrate add()
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

        // before removing print queue
        System.out.println("Queue: " + Q);
    }
}
```

**输出:**

```java
Queue: [7855642, 35658786, 5278367, 74381793]

```

**节目 2:** 借助 **ArrayDeque** 。

```java
// Java Program Demonstrate add()
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

        // before removing print queue
        System.out.println("Queue: " + Q);
    }
}
```

**输出:**

```java
Queue: [7855642, 35658786, 5278367, 74381793]

```

**程序三:**在**的帮助下链接锁定了**。

```java
// Java Program Demonstrate add()
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

        // before removing print queue
        System.out.println("Queue: " + Q);
    }
}
```

**输出:**

```java
Queue: [7855642, 35658786, 5278367, 74381793]

```