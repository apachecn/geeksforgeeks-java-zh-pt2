# Java 中的 PriorityBlockingQueue peek()方法

> 原文:[https://www . geeksforgeeks . org/priorityblockingqueue-peek-method-in-Java/](https://www.geeksforgeeks.org/priorityblockingqueue-peek-method-in-java/)

**[优先级阻塞队列](https://www.geeksforgeeks.org/priorityblockingqueue-class-in-java/)** 的 **peek()** 方法返回优先级阻塞队列的**头**处的元素。它检索 LinkedBlockingQueue 头的值，但不删除它。如果 PriorityBlockingQueue 不包含任何元素，则此方法返回 null。优先级阻塞队列使用与类优先级队列相同的排序规则。

**语法:**

```java
public E peek()
```

**参数:**该方法不取任何参数。

**返回:**该方法返回优先级阻塞队列的**头**。

下面的程序说明了 PriorityBlockingQueue 的 peek()方法。

**例 1:**

```java
// Java Program Demonstrate peek()
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

        // Add elements to PriorityBlockingQueue
        PrioQueue.add(464161);
        PrioQueue.add(416165);

        // print PrioQueue
        System.out.println("PrioQueue: " + PrioQueue);

        // get head of PriorityBlockingQueue
        int head = PrioQueue.peek();

        // print head of PriorityBlockingQueue
        System.out.println("Head of Queue: " + head);
    }
}
```

**Output:**

```java
PrioQueue: [416165, 464161]
Head of Queue: 416165

```

**例 2:** 说明包含名称列表的 PriorityBlockingQueue 的 peek()方法。

```java
// Java Program Demonstrate peek()
// method of PriorityBlockingQueue

import java.util.concurrent.PriorityBlockingQueue;

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

        // print PrioQueue
        System.out.println("List of Names: " + names.toString());

        // get head of PriorityBlockingQueue
        String head = names.peek();

        // print head of PriorityBlockingQueue
        System.out.println("Head of Queue: " + head);

        // remove one name from head
        names.poll();
        System.out.println("First Name from head is removed");

        // print PrioQueue
        System.out.println("List of Names: " + names.toString());

        // get head of PriorityBlockingQueue
        head = names.peek();

        // print head of PriorityBlockingQueue
        System.out.println("Head of Queue: " + head);
    }
}
```

**Output:**

```java
List of Names: [A, Computer, Geeks, forGeeks, Portal]
Head of Queue: A
First Name from head is removed
List of Names: [Computer, Portal, Geeks, forGeeks]
Head of Queue: Computer

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/priorityblockingqueue . html # peek–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/PriorityBlockingQueue.html#peek--)