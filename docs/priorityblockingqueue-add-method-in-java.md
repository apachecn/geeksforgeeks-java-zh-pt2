# Java 中的 PriorityBlockingQueue add()方法

> 原文:[https://www . geeksforgeeks . org/priorityblockingqueue-add-method-in-Java/](https://www.geeksforgeeks.org/priorityblockingqueue-add-method-in-java/)

**优先级阻塞队列**的 **add(E e)** 方法将作为参数传递的元素插入到该优先级阻塞队列的尾部。如果元素的添加成功，此方法返回 true。否则返回假。

**语法:**

```java
public boolean add(E e)
```

**参数:**该方法取一个强制参数 **e** ，该参数是要插入优先级阻塞队列的元素。

**返回:**该方法返回一个**布尔**响应。如果元素添加成功，则返回*真*，否则返回*假*。

**异常:**该方法抛出以下异常:

*   **ClassCastException:** 如果作为参数传递的元素不能与队列包含的元素进行比较以保持优先级队列的顺序。
*   **NullPointRexception:**如果作为参数传递的元素为空。

下面程序举例说明了优先级阻塞队列的 add()方法:

**例 1:**

```java
// Java Program to Demonstrate add(E e) method
// of PriorityBlockingQueue.

import java.util.concurrent.PriorityBlockingQueue;

public class GFG {

    public static void main(String[] args)
    {
        // define capacity of PriorityBlockingQueue
        int capacity = 15;

        // create object of PriorityBlockingQueue
        PriorityBlockingQueue<Integer> PrioBlockingQueue
            = new PriorityBlockingQueue<Integer>(capacity);

        // add  numbers
        PrioBlockingQueue.add(526734);
        PrioBlockingQueue.add(84879456);
        PrioBlockingQueue.add(4586415);

        // print queue after add operation
        System.out.println("After Adding Some Numbers");
        System.out.println("PriorityBlockingQueue:"
                           + PrioBlockingQueue);

        // add more numbers
        PrioBlockingQueue.add(156116);
        PrioBlockingQueue.add(61651191);

        // print queue after add operation
        System.out.println("\nAfter adding Some More Numbers");
        System.out.println("PriorityBlockingQueue:"
                           + PrioBlockingQueue);
    }
}
```

**Output:**

```java
After Adding Some Numbers
PriorityBlockingQueue:[526734, 84879456, 4586415]

After adding Some More Numbers
PriorityBlockingQueue:[156116, 526734, 4586415, 84879456, 61651191]

```

**示例 2:** 演示 add()方法引发的 NullPointerException。

```java
// Java Program to Demonstrate Exception
// thrown by add(E e) method
// of PriorityBlockingQueue.

import java.util.concurrent.PriorityBlockingQueue;

public class GFG {

    public static void main(String[] args)
    {
        // define capacity of PriorityBlockingQueue
        int capacity = 15;

        // create object of PriorityBlockingQueue
        PriorityBlockingQueue<Integer> PrioBlockingQueue
            = new PriorityBlockingQueue<Integer>(capacity);

        // add numbers
        PrioBlockingQueue.add(526734);
        PrioBlockingQueue.add(84879456);
        PrioBlockingQueue.add(4586415);
        try {
            // try to add null to PrioBlockingQueue
            PrioBlockingQueue.add(null);

            // print PrioBlockingQueue after add operation
            System.out.println("PriorityBlockingQueue:"
                               + PrioBlockingQueue);
        }
        catch (Exception e) {
            System.out.println("Exception when adding null: "
                               + e);
        }
    }
}
```

**Output:**

```java
Exception when adding null: java.lang.NullPointerException

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/priorityblockingqueue . html # add-E-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/PriorityBlockingQueue.html#add-E-)