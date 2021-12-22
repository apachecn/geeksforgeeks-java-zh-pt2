# PriorityBlockingQueue 在 Java 中包含()方法

> 原文:[https://www . geeksforgeeks . org/priorityblockingqueue-contains-method-in-Java/](https://www.geeksforgeeks.org/priorityblockingqueue-contains-method-in-java/)

**包含(对象 o)** 方法检查**优先级阻塞队列**是否包含对象 o。此方法返回真，当且仅当，此队列包含至少一个元素 e，该元素等于作为参数传递的对象 o，即 e.equals(o)。如果队列不包含对象 0，则方法返回假。

**语法:**

```
public boolean contains(Object o)
```

**参数:**该方法取的强制参数**，该参数是优先级阻塞队列中要检查的对象。**

**返回:**如果该队列包含作为参数传递的对象，则该方法返回 *true* 。否则返回*假*。

**异常:**此方法不抛出任何异常。

下面的程序说明了包含()方法的优先级阻塞队列:

**例 1:**

```
// Java Program Demonstrate contains(Object o)
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

        // Add element to PriorityBlockingQueue
        PrioQueue.add(4641515);
        PrioQueue.add(46514561);
        PrioQueue.add(56156);
        PrioQueue.add(948964165);

        // print PrioQueue
        System.out.println("PrioQueue: " + PrioQueue);

        // check whether PriorityBlockingQueue contains 56156
        boolean answer1 = PrioQueue.contains(56156);

        // print result
        System.out.println("PriorityBlockingQueue contains "
                           + "number 56156 : "
                           + answer1);

        // check whether PriorityBlockingQueue contains 46545
        boolean answer2 = PrioQueue.contains(46545);

        // print result
        System.out.println("PriorityBlockingQueue contains"
                           + " number 46545 : "
                           + answer2);
    }
}
```

**Output:**

```
PrioQueue: [56156, 46514561, 4641515, 948964165]
PriorityBlockingQueue contains number 56156 : true
PriorityBlockingQueue contains number 46545 : false

```

**示例 2:** 演示包含名称列表的 PriorityBlockingQueue 的 contains()方法。

```
// Java Program Demonstrate contains(Object o)
// method of PriorityBlockingQueue

import java.util.concurrent.PriorityBlockingQueue;

public class GFG {

    public static void main(String[] args)
    {
        // define capacity of PriorityBlockingQueue
        int capacityOfQueue = 10;

        // create object of PriorityBlockingQueue
        PriorityBlockingQueue<String> names
            = new PriorityBlockingQueue<String>(capacityOfQueue);

        // Add names
        names.add("Geeks");
        names.add("forGeeks");
        names.add("A");
        names.add("Computer");
        names.add("Portal");

        // print queue details
        System.out.println("List of Names: " + names);

        // check whether PriorityBlockingQueue contains Geeks
        boolean answer1 = names.contains("Geeks");

        // print result
        System.out.println("Does names contains "
                           + "Geeks: "
                           + answer1);

        // check whether PriorityBlockingQueue contains SandeepJain
        boolean answer2 = names.contains("SandeepJain");

        // print result
        System.out.println("Does names contains "
                           + "SandeepJain: "
                           + answer2);
    }
}
```

**Output:**

```
List of Names: [A, Computer, Geeks, forGeeks, Portal]
Does names contains Geeks: true
Does names contains SandeepJain: false

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/priorityblockingqueue . html # contains-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/PriorityBlockingQueue.html#contains-java.lang.Object-)