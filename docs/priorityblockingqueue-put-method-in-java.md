# Java 中的 PriorityBlockingQueue put()方法

> 原文:[https://www . geeksforgeeks . org/priorityblockingqueue-put-method-in-Java/](https://www.geeksforgeeks.org/priorityblockingqueue-put-method-in-java/)

[**优先级阻塞队列**](https://www.geeksforgeeks.org/priorityblockingqueue-class-in-java/) 的 **put(E e)** 方法用于**向该队列**中添加一个元素。此方法将指定的元素插入到该优先级队列中。由于队列是无界的，这个方法永远不会被阻塞。
**语法:**

```
public void put(E e)
```

**参数:**该方法接受一个强制参数 **e** ，该参数是要插入优先级阻塞队列的元素。
**返回值:**该方法不返回任何内容。
**异常:**此方法抛出以下异常:

*   **class castexception**–如果指定的元素不能根据优先级队列的顺序与当前在优先级队列中的元素进行比较。
*   **NullPointRexception**–如果指定的元素为空。

下面的程序举例说明了 PriorityBlockingQueue 中的 put()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate put(E e)
// method of PriorityBlockingQueue

import java.util.concurrent.PriorityBlockingQueue;

public class GFG {
    public static void main(String[] args)
    {

        // create object of PriorityBlockingQueue
        PriorityBlockingQueue<Integer> pbq
            = new PriorityBlockingQueue<Integer>();

        // Add element using put() method
        pbq.put(1);
        pbq.put(2);
        pbq.put(3);
        pbq.put(4);

        // print elements of queue
        System.out.println("Queue: " + pbq);
    }
}
```

**Output:** 

```
Queue: [1, 2, 3, 4]
```

**程序 2:** 演示空指针异常

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Demonstrate put(E e)
// method of PriorityBlockingQueue

import java.util.concurrent.PriorityBlockingQueue;

public class GFG {
    public static void main(String[] args)
    {

        // create object of PriorityBlockingQueue
        PriorityBlockingQueue<String> pbq
            = new PriorityBlockingQueue<String>();

        // try to put null value in put method
        try {
            pbq.put(null);
        }
        catch (Exception e) {
            // print error details
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:** 

```
Exception: java.lang.NullPointerException
```