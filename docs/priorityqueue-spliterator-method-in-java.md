# Java 中的 PriorityQueue spliterator()方法

> 原文:[https://www . geesforgeks . org/priorityqueue-spliterator-method-in-Java/](https://www.geeksforgeeks.org/priorityqueue-spliterator-method-in-java/)

PriorityQueue 的**拆分器()**方法返回一个与 PriorityQueue 元素相同的**拆分器。返回的拆分器是**后期绑定和快速失效**拆分器。后期绑定拆分器绑定到元素源意味着在第一次遍历、第一次拆分或第一次查询估计大小时的优先级队列，而不是在创建拆分器时。它可以和 Java 8 中的 Streams 一起使用。此外，它还可以单独和批量遍历元素。Spliterator 是遍历元素的更好方法，因为它对元素提供了更多的控制。**

**语法:**

```
public Spliterator<E> spliterator()
```

**返回:**这个方法在 PriorityQueue 中的元素上返回一个拆分器。

下面的程序说明了优先级队列的 spliterator()方法:

**示例 1:** 演示 PriorityQueue 上的 spliterator()方法。

```
// Java Program Demonstrate spliterator()
// method of PriorityQueue

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an PriorityQueue
        PriorityQueue<String> queue = new PriorityQueue<String>();

        // Add String to queue
        queue.add("Kolkata");
        queue.add("Patna");
        queue.add("Delhi");
        queue.add("Jammu");

        // using spliterator() method
        Spliterator<String> spt = queue.spliterator();

        // print result from Spliterator
        System.out.println("list of Strings:");

        // forEachRemaining method of Spliterator
        spt.forEachRemaining((n) -> System.out.println(n));
    }
}
```

**输出:**

```
list of Strings:
Delhi
Jammu
Kolkata
Patna

```

**示例 2:** 演示包含一组学生姓名的优先级队列上的拆分器()方法。

```
// Java Program Demonstrate spliterator()
// method of PriorityQueue

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an PriorityQueue which going to
        // contain list of names
        PriorityQueue<String> queue = new PriorityQueue<String>();

        // Add String object to queue
        queue.add("Aman");
        queue.add("Amar");
        queue.add("Sanjeet");
        queue.add("Josh");
        queue.add("Ron");
        queue.add("Kevin");

        // using spliterator() method
        Spliterator<String> spt = queue.spliterator();

        // print result from Spliterator
        System.out.println("list of String Object:");

        // forEachRemaining method of Spliterator
        spt.forEachRemaining((n) -> print(n));
    }

    public static void print(String s)
    {
        System.out.println("Student Name: " + s);
    }
}
```

**输出:**

```
list of String Object:
Student Name: Aman
Student Name: Amar
Student Name: Kevin
Student Name: Josh
Student Name: Ron
Student Name: Sanjeet

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/priorityqueue . html # spliterator–](https://docs.oracle.com/javase/8/docs/api/java/util/PriorityQueue.html#spliterator--)