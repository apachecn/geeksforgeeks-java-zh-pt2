# Java 中的 PriorityBlockingQueue spliterator()方法

> 原文:[https://www . geeksforgeeks . org/priorityblockingqueue-spliterator-method-in-Java/](https://www.geeksforgeeks.org/priorityblockingqueue-spliterator-method-in-java/)

**[优先级阻塞队列](https://www.geeksforgeeks.org/priorityblockingqueue-class-in-java/)** 的**拆分器()**方法返回一个与优先级阻塞队列相同元素的**拆分器**。返回的迭代器弱一致。它可以和 Java 8 中的 Streams 一起使用。此外，它还可以单独和批量遍历元素。Spliterator 是遍历元素的更好方法，因为它对元素提供了更多的控制。

**语法:**

```
public Spliterator spliterator()
```

**返回:**这个方法在 PriorityBlockingQueue 中的元素上返回一个拆分器。

下面的程序说明了 PriorityBlockingQueue 的 spliterator()方法:

**示例 1:** 在包含数字列表的 PriorityBlockingQueue 上演示 spliterator()方法的程序。

```
// Java Program Demonstrate spliterator()
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

        // Add numbers to PriorityBlockingQueue
        PrioQueue.put(7855642);
        PrioQueue.put(35658786);
        PrioQueue.put(5278367);
        PrioQueue.put(74381793);
        PrioQueue.put(76487590);
        PrioQueue.put(87625142);

        // create Spliterator of PrioQueue
        // using spliterator() method
        Spliterator<Integer> numbers = PrioQueue.spliterator();

        // print result from Spliterator
        System.out.println("list of Numbers:");

        // forEachRemaining method  of Spliterator
        numbers.forEachRemaining((n) -> System.out.println(n));
    }
}
```

**输出:**

```
list of Numbers:
5278367
35658786
7855642
74381793
76487590
87625142

```

**示例 2:** 在包含名称列表的 PriorityBlockingQueue 上演示 spliterator()方法的程序。

```
// Java Program Demonstrate spliterator()
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
        names.add("Joyita");
        names.add("Priyanka");
        names.add("Joydeep");

        // create Spliterator of PrioQueue
        // using spliterator() method
        Spliterator<String> list = names.spliterator();

        // print result from Spliterator
        System.out.println("list of Names:");

        // forEachRemaining method  of Spliterator
        list.forEachRemaining((n) -> System.out.println(n));
    }
}
```

**输出:**

```
list of Names:
Joydeep
Priyanka
Joyita

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/priorityblockingqueue . html # spliterator–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/PriorityBlockingQueue.html#spliterator--)