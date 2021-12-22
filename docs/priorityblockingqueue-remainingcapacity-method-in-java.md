# Java 中的 PriorityBlockingQueue remaingccapacity()方法

> 原文:[https://www . geeksforgeeks . org/priorityblockingqueue-remainingcapacity-method-in-Java/](https://www.geeksforgeeks.org/priorityblockingqueue-remainingcapacity-method-in-java/)

[**优先级阻塞队列**](https://www.geeksforgeeks.org/priorityblockingqueue-class-in-java/) 的**剩余容量**方法用于检查**该队列还能插入多少元素。**但是由于 PriorityBlockingQueue 是无界的，这个方法总是返回**整数。最大值**因为优先级阻塞队列不受容量限制。
**语法:**

```java
public int remainingCapacity()
```

**返回值:**整数。最大值始终
下面的程序说明了优先级阻塞队列中的剩余容量()方法:
T4】程序 1:T6】

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate remainingCapacity()
// method of PriorityBlockingQueue

import java.util.concurrent.PriorityBlockingQueue;

public class GFG {
    public static void main(String[] args)
    {
        // define capacity of PriorityBlockingQueue
        int capacityOfQueue = 7;

        // create object of PriorityBlockingQueue
        PriorityBlockingQueue<Integer> pbq
            = new PriorityBlockingQueue<Integer>(capacityOfQueue);

        // Add element to PriorityBlockingQueue
        pbq.put(1);
        pbq.put(2);
        pbq.put(3);
        pbq.put(4);

        // find remaining Capacity  of pbq
        // using remainingCapacity() method

        // The initial capacity was set to 7
        // by passing as parameter in constructor
        // But this method will return Integer.MAX_VALUE
        int remainingCapacity = pbq.remainingCapacity();

        // print result
        System.out.println("Queue:  " + pbq);
        System.out.println("Remaining Capacity: " + remainingCapacity);
    }
}
```

**Output:** 

```java
Queue:  [1, 2, 3, 4]
Remaining Capacity: 2147483647
```

**程序 2:** 使用字符串
演示剩余容量()

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Demonstrate remainingCapacity()
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

        // find remaining Capacity  of pbq
        // using remainingCapacity() method
        int remainingCapacity = pbq.remainingCapacity();

        // print result
        System.out.println("Queue:  " + pbq);
        System.out.println("Remaining Capacity: " + remainingCapacity);
    }
}
```

**Output:** 

```java
Queue:  [A Computer, Portal, Geeks, forGeeks]
Remaining Capacity: 2147483647
```