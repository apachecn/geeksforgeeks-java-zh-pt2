# Java 中的 PriorityBlockingQueue 迭代器()方法

> 原文:[https://www . geeksforgeeks . org/priorityblockingqueue-iterator-method-in-Java/](https://www.geeksforgeeks.org/priorityblockingqueue-iterator-method-in-java/)

**[PriorityBlockingQueue](https://www.geeksforgeeks.org/priorityblockingqueue-class-in-java/)**类的**迭代器()**方法返回该队列中元素的迭代器。从该方法返回的元素不遵循任何顺序。返回的迭代器弱一致。

**语法:**

```java
public Iterator iterator()
```

**参数:**该方法不取任何参数。

**返回:**该方法返回一个**迭代器**，其元素与优先级阻塞队列中的元素相同。

下面的程序说明了 PriorityBlockingQueue 的迭代器()方法。

**例 1:**

```java
// Java Program Demonstrate iterator()
// method of PriorityBlockingQueue

import java.util.concurrent.PriorityBlockingQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // define capacity of PriorityBlockingQueue
        int capacityOfQueue = 5;

        // create object of PriorityBlockingQueue
        PriorityBlockingQueue<Integer> PrioQueue
            = new PriorityBlockingQueue<Integer>(capacityOfQueue);

        // Add elements to PriorityBlockingQueue
        PrioQueue.add(945645);
        PrioQueue.add(6468516);
        PrioQueue.add(7564165);
        PrioQueue.add(45616);

        // print PrioQueue
        System.out.println("PrioQueue: " + PrioQueue);

        // Call iterator() method of PriorityBlockingQueue
        Iterator iteratorVals = PrioQueue.iterator();

        // Print elements of iterator
        // created from PriorityBlockingQueue
        System.out.println("The iterator values"
                           + " of PriorityBlockingQueue are:");

        while (iteratorVals.hasNext()) {
            System.out.println(iteratorVals.next());
        }
    }
}
```

**Output:**

```java
PrioQueue: [45616, 945645, 7564165, 6468516]
The iterator values of PriorityBlockingQueue are:
45616
945645
7564165
6468516

```

**例 2:** 说明包含名称列表的 PriorityBlockingQueue 的迭代器()方法。

```java
// Java Program Demonstrate iterator()
// method of PriorityBlockingQueue

import java.util.concurrent.PriorityBlockingQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // define capacity of PriorityBlockingQueue
        int capacityOfQueue = 5;

        // create object of PriorityBlockingQueue
        PriorityBlockingQueue<String> names
            = new PriorityBlockingQueue<String>(capacityOfQueue);

        // Add names of students of girls college
        names.add("Geeks");
        names.add("forGeeks");
        names.add("A");
        names.add("Computer");
        names.add("Portal");

        // Call iterator() method of PriorityBlockingQueue
        Iterator iteratorVals = names.iterator();

        // Print elements of iterator
        // created from PriorityBlockingQueue
        System.out.println("The Names are:");

        while (iteratorVals.hasNext()) {
            System.out.println(iteratorVals.next());
        }
    }
}
```

**Output:**

```java
The Names are:
A
Computer
Geeks
forGeeks
Portal

```

**相关文章:**

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/priorityblockingqueue . html #迭代器–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/PriorityBlockingQueue.html#iterator--)