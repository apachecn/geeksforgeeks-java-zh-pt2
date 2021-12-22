# Java 中的 PriorityBlockingQueue toString()方法

> 原文:[https://www . geeksforgeeks . org/priorityblockingqueue-tostring-method-in-Java/](https://www.geeksforgeeks.org/priorityblockingqueue-tostring-method-in-java/)

**[PriorityBlockingQueue](https://www.geeksforgeeks.org/priorityblockingqueue-class-in-java/)**的 **toString()** 方法返回该 PriorityBlockingQueue 的字符串表示，显示 PriorityBlockingQueue 包含的元素的详细信息。PriorityBlockingQueue 的字符串包含 PriorityBlockingQueue 的元素，其顺序与其迭代器返回的顺序相同，用方括号(“[]”)括起来。元素由字符“，”(逗号和空格)分隔。所以基本上 toString()方法用于将 PriorityBlockingQueue 的所有元素转换成一个字符串。

**语法:**

```java
public String toString()
```

**返回:**这个方法返回一个**字符串**，代表这个优先级阻塞队列的元素。

下面的程序说明了优先级阻塞队列的 toString()方法:

**示例 1:** 演示包含整数列表的 PriorityBlockingQueue 上的 toString()方法。

```java
// Java Program Demonstrate toString()
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

        // print Details
        System.out.println("String representation: " + str);
    }
}
```

**Output:**

```java
String representation: [4594591, 9459156, 4981561, 45815616]

```

**示例 2:** 演示包含字符串列表的 PriorityBlockingQueue 上的 toString()方法

```java
// Java Program Demonstrate toString()
// method of PriorityBlockingQueue

import java.util.concurrent.PriorityBlockingQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of PriorityBlockingQueue
        // which contains Strings
        PriorityBlockingQueue<String> names
            = new PriorityBlockingQueue<String>();

        // Add Strings
        names.add("Geeks");
        names.add("forGeeks");
        names.add("A Computer Portal");
        names.add("By Sandeep Jain");

        // get String representation of PriorityBlockingQueue
        String str = names.toString();

        // print Details
        System.out.println("String representation: " + str);
    }
}
```

**Output:**

```java
String representation: [A Computer Portal, By Sandeep Jain, Geeks, forGeeks]

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/priorityblockingqueue . html # toString–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/PriorityBlockingQueue.html#toString--)