# Java 中的 PriorityBlockingQueue offer()方法

> 原文:[https://www . geeksforgeeks . org/priorityblockingqueue-offer-method-in-Java/](https://www.geeksforgeeks.org/priorityblockingqueue-offer-method-in-java/)

### 1.报价方法

[优先级阻塞队列](https://www.geeksforgeeks.org/priorityblockingqueue-class-in-java/) **的 **offer(E e)** 方法将作为参数传递的元素 e** 插入到该优先级阻塞队列中。这个方法将元素插入这个优先级阻塞队列。由于 PriorityBlockingQueue 是无界的，因此永远不会阻止此方法。

**语法:**

```
public boolean offer(E e)
```

**参数:**
这个方法接受一个参数 **e** ，这个参数代表我们要插入到这个 PriorityBlockingQueue 中的元素 e。

**返回:**
如果插入成功，该方法返回布尔响应 true。

**异常:**该方法抛出以下异常。

*   **class castexception**–如果指定的元素无法根据 PriorityBlockingQueue 的顺序与优先级队列中的当前元素进行比较。
*   **空指针异常**–如果元素为空

下面的程序说明了优先级阻塞队列的 offer()方法:

**示例 1:** 在 PriorityBlockingQueue 上演示 offer()方法以添加数字列表的程序。

```
// Java Program Demonstrate offer()
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

        // Add numbers to PriorityBlockingQueue using offer()
        PrioQueue.offer(35658786);
        PrioQueue.offer(5278367);
        PrioQueue.offer(74381793);
        PrioQueue.offer(87625142);

        // print elements of PriorityBlockingQueue
        System.out.println("Queue Contains:");
        System.out.println(PrioQueue.toString());
    }
}
```

**Output:**

```
Queue Contains:
[5278367, 35658786, 74381793, 87625142]

```

**示例 2:** 程序演示当我们试图向 PriorityBlockingQueue 添加 null 时，offer()方法引发的异常。

```
// Java Program Demonstrate offer()
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

        // try to insert null value in offer method
        try {
            names.offer(null);
        }
        catch (Exception e) {
            // print error details
            System.out.println("Exception Thrown: " + e);
        }
    }
}
```

**Output:**

```
Exception Thrown: java.lang.NullPointerException

```

### 2.报价(例如，长超时，时间单位单位)方法

[优先级阻塞队列](https://www.geeksforgeeks.org/priorityblockingqueue-class-in-java/) **的**提供(E e，长超时，时间单位单位)**方法在该优先级阻塞队列中插入作为参数传递的元素 e** 。这个方法将元素插入这个优先级阻塞队列。因为优先级阻塞队列是无界的，所以这个方法永远不会被阻塞，超时和时间单位参数被忽略。此方法继承自 priorityBlockingQueue 的超级队列，该队列是 BlockingQueue 类，但由于 priorityBlockingQueue 从不阻止要插入的新元素，因此从 super 类继承的此方法在逻辑上与 offer(E e)方法相同。

**语法:**

```
offer(E e, long timeout, TimeUnit unit)
```

**参数:**该方法接受三个参数

1.  **e** :优先阻塞队列中要插入的元素。
2.  **超时**:该参数被忽略，因为队列从不阻止新元素插入。
3.  **单元**:这个参数也被忽略了，因为队列从来不会阻塞新元素的插入。

**返回:**如果插入成功，该方法返回布尔响应 true。

**异常:**该方法抛出以下异常。

*   **class castexception**–如果指定的元素无法根据 PriorityBlockingQueue 的顺序与优先级队列中的当前元素进行比较。
*   **空指针异常**–如果元素为空

下面的程序说明了优先级阻塞队列的提供(例如，长超时，时间单位单位)方法:

**示例 1:** 在优先级阻塞队列上演示报价(E e，长超时，时间单位单位)方法以添加数字列表的程序。

```
// Java Program Demonstrate offer()
// method of PriorityBlockingQueue

import java.util.concurrent.PriorityBlockingQueue;
import java.util.concurrent.TimeUnit;

public class GFG {
    public static void main(String[] args)
    {

        // define capacity of PriorityBlockingQueue
        int capacityOfQueue = 5;

        // create object of PriorityBlockingQueue
        PriorityBlockingQueue<Integer> PrioQueue
            = new PriorityBlockingQueue<Integer>(capacityOfQueue);

        // Add 3 elements to PriorityBlockingQueue using
        // offer(Element e, long timeout, TimeUnit unit)
        System.out.println("adding 1234 "
                           + PrioQueue.offer(1234,
                                             5, TimeUnit.SECONDS));
        System.out.println("adding 2345 "
                           + PrioQueue.offer(2345,
                                             5, TimeUnit.SECONDS));
        System.out.println("adding 3456 "
                           + PrioQueue.offer(3456,
                                             5, TimeUnit.SECONDS));

        // print elements of PriorityBlockingQueue
        System.out.println("Queue Contains:");
        System.out.println(PrioQueue.toString());
    }
}
```

**Output:**

```
adding 1234 true
adding 2345 true
adding 3456 true
Queue Contains:
[1234, 2345, 3456]

```

**参考:**

*   [https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/priorityblockingqueue . html # offer-E-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/PriorityBlockingQueue.html#offer-E-)
*   [https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/priorityblockingqueue . html # offer-E-long-Java . util . concurrent . time unit-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/PriorityBlockingQueue.html#offer-E-long-java.util.concurrent.TimeUnit-)