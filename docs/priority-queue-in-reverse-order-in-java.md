# Java 中的逆序优先队列

> 原文:[https://www . geesforgeks . org/priority-queue-in-reverse-in-Java/](https://www.geeksforgeeks.org/priority-queue-in-reverse-order-in-java/)

当根据优先级应该处理对象时，使用[优先级队列](https://www.geeksforgeeks.org/priority-queue-set-1-introduction/)。众所周知[队列](https://www.geeksforgeeks.org/queue-interface-java/)遵循先进先出算法，但有时需要根据优先级处理队列的元素，这就是优先级队列的作用。优先级队列基于优先级堆。优先级队列的元素根据自然顺序进行排序，或者由队列构建时提供的[比较器](https://www.geeksforgeeks.org/comparator-interface-java/)进行排序，具体取决于使用的构造器。

![Hierarchy of Priority Queue](img/60cee2c4d09185f472d67be6d39b42a1.png)

**申报:**

```
public class PriorityQueue<E> extends AbstractQueue<E> implements Serializable
```

其中 **E** 是该队列中保存的元素类型

**优先级队列的类型**

*   最大优先级队列
*   最小优先级队列

**默认优先级队列示例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the
// working of default PriorityQueue
import java.util.*;

class PriorityQueueDemo {

    // Main Method
    public static void main(String args[])
    {
        // Creating empty priority queue
        PriorityQueue<Integer> pQueue
            = new PriorityQueue<Integer>();

        // Adding items to the pQueue using add()
        pQueue.add(10);
        pQueue.add(20);
        pQueue.add(15);
        pQueue.add(5);

        // Printing the top element of PriorityQueue
        System.out.println(pQueue.peek());

        // Printing the top element and removing it
        // from the PriorityQueue container
        System.out.println(pQueue.poll());

        // Printing the top element again
        System.out.println(pQueue.peek());
    }
}
```

**Output**

```
5
5
10
```

在 Java 中，优先级队列默认实现最小优先级队列，如果我们需要将优先级队列的顺序从最小更改为最大优先级队列，那么我们使用如下方法:

*   使用默认的比较器集合
*   使用自定义比较器
*   使用λ表达式

**方法 1:** **使用默认比较器集合. reverseOrder()**

[collections . reverse order()](https://www.geeksforgeeks.org/collections-reverseorder-java-examples/)方法用于获取默认比较器的反向行为。这是 [java.util 包](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/java-util-package-java/&sa=U&ved=2ahUKEwi1vNjU-5DtAhVI4zgGHfSfD40QFjAAegQIBBAB&usg=AOvVaw1Q1cmtJYaXyYcifq_dK1Ev) 中的一个默认比较器。

**例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the
// working of PriorityQueue in reverse order
import java.util.*;

class PriorityQueueDemo {

    // Main Method
    public static void main(String args[])
    {
        // Creating empty priority queue
        PriorityQueue<Integer> pQueue
            = new PriorityQueue<Integer>(
                Collections.reverseOrder());

        // Adding items to the pQueue using add()
        pQueue.add(10);
        pQueue.add(20);
        pQueue.add(15);
        pQueue.add(5);

        // Printing the top element of PriorityQueue
        System.out.println(pQueue.peek());

        // Printing the top element and removing it
        // from the PriorityQueue container
        System.out.println(pQueue.poll());

        // Printing the top element again
        System.out.println(pQueue.peek());
    }
}
```

**Output**

```
20
20
15
```