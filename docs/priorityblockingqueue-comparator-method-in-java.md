# Java 中的 PriorityBlockingQueue 比较器()方法

> 原文:[https://www . geeksforgeeks . org/priorityblockingqueue-comparator-in-method-in-Java/](https://www.geeksforgeeks.org/priorityblockingqueue-comparator-method-in-java/)

**[优先级阻塞队列](https://www.geeksforgeeks.org/priorityblockingqueue-class-in-java/)** 的**比较器()**方法返回可用于对优先级阻塞队列中的元素进行排序的比较器。如果队列遵循元素的自然排序模式，则该方法返回**空值**。

**语法:**

```
public Comparator<? super E> comparator()
```

**返回:**该方法返回**比较器集合**，用于以特定顺序对集合中的元素进行排序。如果优先级阻塞队列遵循默认或自然的排序模式，它将返回一个**空值**。

下面的程序说明了优先级阻塞队列的比较器()方法:

**示例 1:** 演示包含整数列表的 PriorityBlockingQueue 上的比较器()方法。

```
// Java Program Demonstrate comparator()
// method of PriorityBlockingQueue

import java.util.concurrent.PriorityBlockingQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of PriorityBlockingQueue
        PriorityBlockingQueue<Integer> PrioQueue
            = new PriorityBlockingQueue<Integer>();

        // Add numbers to PriorityBlockingQueue
        PrioQueue.put(45815616);
        PrioQueue.put(4981561);
        PrioQueue.put(4594591);
        PrioQueue.put(9459156);

        // get String representation of PriorityBlockingQueue
        String str = PrioQueue.toString();

        // Creating a comparator using comparator()
        Comparator comp = PrioQueue.comparator();

        // Displaying the comparator values
        System.out.println("Comparator value: " + comp);

        if (comp == null)
            System.out.println("PriorityBlockingQueue"
                               + "follows natural ordering");
        else
            System.out.println("PriorityBlockingQueue follows"
                               + comp);
    }
}
```

**输出:**

```
Comparator value: null
PriorityBlockingQueuefollows natural ordering

```

**示例 2:** 演示包含字符串列表的 PriorityBlockingQueue 上的 toString()方法。

```
// Java Program Demonstrate comparator()
// method of PriorityBlockingQueue

import java.util.concurrent.PriorityBlockingQueue;
import java.util.*;

// Comparator to compare Strings
class COMPARING implements Comparator<String> {
    public int compare(String str1, String str2)
    {
        return str2.compareTo(str1);
    }
}

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // define capacity of PriorityBlockingQueue
        int capacityOfQueue = 5;

        // create object of PriorityBlockingQueue
        // by passing capacity and comparator class
        // as parameters.
        PriorityBlockingQueue<String> characters
            = new PriorityBlockingQueue<String>(capacityOfQueue,
                                                new COMPARING());

        // Add Strings
        characters.add("Geeks");
        characters.add("forGeeks");
        characters.add("A computer portal");

        // Getting the comparator using comparator()
        Comparator comp = characters.comparator();

        // Displaying the comparator values
        System.out.println("Comparator value is: " + comp);

        if (comp == null)
            System.out.println("PriorityBlockingQueue"
                               + "follows natural ordering");
        else
            System.out.println("PriorityBlockingQueue follows: "
                               + comp);
        // display result
        System.out.println("\nThe elements after custom Comparator");
        for (String e : characters)
            System.out.print(e + ", ");
    }
}
```

**输出:**

```
Comparator value is: COMPARING@28d93b30
PriorityBlockingQueue follows: COMPARING@28d93b30

The elements after custom Comparator
forGeeks, Geeks, A computer portal,

```