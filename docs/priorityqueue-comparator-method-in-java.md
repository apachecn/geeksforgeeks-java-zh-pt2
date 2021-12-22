# Java 中的优先级队列比较器()方法

> 原文:[https://www . geesforgeks . org/priorityqueue-comparator-in-method-in-Java/](https://www.geeksforgeeks.org/priorityqueue-comparator-method-in-java/)

Java . util . PriorityQueue . comparator()方法共享一个重要的功能，即设置并返回比较器，该比较器可用于对 [PriorityQueue](https://www.geeksforgeeks.org/priority-queue-class-in-java-2/) 中的元素进行排序。如果队列遵循元素的自然排序模式，则方法返回空值。
**语法:**

```java
comp_set = (PriorityQueue)Priority_Queue.comparator()
```

**参数:**该方法不取任何参数。
**返回值:**该方法返回用于以特定顺序对队列元素进行排序的比较器。如果队列遵循默认或自然的排序模式，它将返回空值。
下面的程序说明了 Java . util . priority queue . comparator()方法:
**程序 1:** 当使用元素的自然排序时:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate comparator()
import java.util.*;

public class Priority_Queue_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Priority_Queue
        PriorityQueue<Integer> queue = new PriorityQueue<Integer>();

        // Adding elements to the queue
        queue.add(20);
        queue.add(24);
        queue.add(30);
        queue.add(35);
        queue.add(45);
        queue.add(50);

        System.out.println("Priority queue values are: " + queue);

        // Creating a comparator
        Comparator comp = queue.comparator();

        // Displaying the comparator values
        System.out.println("Since the Comparator value is: " + comp);
        System.out.println("it follows natural ordering");
    }
}
```

**Output:** 

```java
Priority queue values are: [20, 24, 30, 35, 45, 50]
Since the Comparator value is: null
it follows natural ordering
```

**程序 2:** 当使用特定的[比较器](https://www.geeksforgeeks.org/implement-priorityqueue-comparator-java/)时。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate the use of comparator()
import java.util.Comparator;
import java.util.PriorityQueue;

class The_Comparator implements Comparator<String> {
    public int compare(String str1, String str2)
    {
        String first_Str;
        String second_Str;
        first_Str = str1;
        second_Str = str2;
        return second_Str.compareTo(first_Str);
    }
}

public class Priority_Queue_Demo {
    public static void main(String[] args)
    {
        PriorityQueue<String> queue = new
        PriorityQueue<String>(new The_Comparator());

        queue.add("G");
        queue.add("E");
        queue.add("E");
        queue.add("K");
        queue.add("S");
        queue.add("4");

        System.out.println("The elements with the highest priority element at front of queue"
                           + "order:");
        while(!queue.isEmpty()){
          System.out.print(" "+queue.poll());
        }
    }
}
```

**Output**

```java
The elements with the highest priority element at front of queueorder:
 S K G E E 4
```