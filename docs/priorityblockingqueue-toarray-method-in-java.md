# Java 中的 PriorityBlockingQueue toArray()方法

> 原文:[https://www . geeksforgeeks . org/priorityblockingqueue-to array-method-in-Java/](https://www.geeksforgeeks.org/priorityblockingqueue-toarray-method-in-java/)

### toarray()

PriorityBlockingQueue 的**到 Array** 方法用于创建一个数组，该数组具有与该 PriorityBlockingQueue 相同的元素，并按适当的顺序排列。实际上，这个方法将 PriorityBlockingQueue 中的所有元素复制到一个新数组中。此方法充当数组和优先级阻塞队列之间的桥梁。

**语法:**

```java
public Object[] toArray()
```

**返回值:**这个方法返回一个包含 PriorityBlockingQueue 元素的数组。

下面的程序说明了优先级阻塞队列类的 Array()方法:

**示例 1:** 演示优先级阻塞队列的 toArray()方法的程序，用于从包含数字的优先级阻塞队列创建数字数组。

## Java

```java
// Java Program Demonstrate toArray()
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

        // Add numbers to PriorityBlockingQueue
        PrioQueue.offer(35658786);
        PrioQueue.offer(5278367);
        PrioQueue.offer(74381793);
        PrioQueue.offer(87625142);

        // create an array of elements of PriorityBlockingQueue
        Object[] array = PrioQueue.toArray();

        // print elements of array
        System.out.println("Array Contains:");
        for (Object i : array) {
            System.out.print(i + " ");
        }
    }
}
```

**输出:**

```java
Array Contains:
5278367 35658786 74381793 87625142
```

**示例 2:** 演示优先级阻塞队列的 toArray()方法的程序，用于从包含字符串值的优先级阻塞队列创建字符串数组。

## Java

```java
// Java Program Demonstrate toArray()
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
        names.offer("Joyita");
        names.offer("Bristi");
        names.offer("Riya");

        // Create a array by calling toArray() method
        Object[] array = names.toArray();

        // Print List of names
        System.out.println("Queue is " + names);

        // Print elements of array
        System.out.println("The array created by toArray() is:");
        for (Object i : array) {
            System.out.println(i + " ");
        }
    }
}
```

**输出:**

```java
Queue is [Bristi, Joyita, Riya]
The array created by toArray() is:
Bristi 
Joyita 
Riya
```

### toaarray(t[]a)

**PriorityBlockingQueue** 的 toArray(T[] a)方法用于以适当的顺序返回包含与该 PriorityBlockingQueue 相同元素的数组。此方法与 toArray()的区别仅在于一个条件。如果 PriorityBlockingQueue 的大小小于或等于传递的数组，则返回的数组的类型与参数中传递的数组相同。否则，将分配一个与指定数组类型相同的新数组，并且该数组的大小等于该队列的大小。此方法充当数组和集合之间的桥梁。

**语法:**

```java
public <T> T[] toArray(T[] a)
```

**参数:**该方法以一个**数组**为参数，如果队列足够大，队列的所有元素都将被复制到该数组中。否则，会为此分配一个相同运行时类型的新数组。

**返回值:**这个方法返回一个包含这个队列中所有元素的数组。

**异常**当传递的数组与 PriorityBlockingQueue 的元素类型不同时，该方法抛出以下异常:

*   **array storeexception:**。
*   **Null pointer exception:** If the passed array is empty.

下面的程序说明了优先级阻塞队列类的数组方法:

**示例 1:** 在优先级阻塞队列上演示 toArray(T[] a)方法的程序。

## Java

```java
// Java Program Demonstrate toArray(T[] a)
// method of PriorityBlockingQueue

import java.util.concurrent.PriorityBlockingQueue;
import java.util.concurrent.TimeUnit;

public class GFG {

    public static void main(String[] args)
        throws InterruptedException
    {
        // define capacity of PriorityBlockingQueue
        int capacityOfQueue = 3;

        // create object of PriorityBlockingQueue
        PriorityBlockingQueue<String> PrioQueue
            = new PriorityBlockingQueue<String>(capacityOfQueue);

        // Add names of students of girls college
        PrioQueue.offer("Joyi");
        PrioQueue.offer("Rani");
        PrioQueue.offer("Riya");

        // Creating the array
        String[] array = new String[capacityOfQueue];

        // Calling toArray(T[] a) method
        Object[] ReturnArray = PrioQueue.toArray(array);

        // Print queue
        System.out.println("Queue is " + PrioQueue);

        // Print elements of array passed as parameter
        System.out.println();
        System.out.println("The array passed to toArray() is:");
        for (Object i : array) {
            System.out.println(i);
        }

        // Print elements of array returned by method toArray()
        System.out.println();
        System.out.println("The array returned by toArray() is:");
        for (Object i : ReturnArray) {
            System.out.println(i);
        }
    }
}
```

**输出**

```java
Queue is [Joyi, Rani, Riya]

The array passed to toArray() is:
Joyi
Rani
Riya

The array returned by toArray() is:
Joyi
Rani
Riya
```

**示例 2:** 演示优先级阻塞队列的 toArray(T[] a)方法引发的异常的程序。

## Java

```java
// Java Program Demonstrate toArray(T[] a)
// method of PriorityBlockingQueue

import java.util.concurrent.PriorityBlockingQueue;
import java.util.concurrent.TimeUnit;

public class GFG {

    public static void main(String[] args)
        throws InterruptedException
    {
        // define capacity of PriorityBlockingQueue
        int capacityOfQueue = 3;

        // create object of PriorityBlockingQueue
        PriorityBlockingQueue<String> PrioQueue
            = new PriorityBlockingQueue<String>(capacityOfQueue);

        // Add names of students of girls college
        PrioQueue.offer("Joyi");
        PrioQueue.offer("Rani");
        PrioQueue.offer("Riya");

        // Creating the array with null value
        String[] array = null;

        try {
            // Calling toArray(T[] a) method
            Object[] ReturnArray = PrioQueue.toArray(array);
        }
        catch (Exception e) {
            System.out.println("Exception thrown:" + e);
        }
    }
}
```

**输出:**

```java
Exception thrown:java.lang.NullPointerException
```

**参考:**

*   [https://docs。甲骨文。com/javase/8/docs/API/Java/util/concurrent/priorityblockingqueue。html # to array–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/PriorityBlockingQueue.html#toArray--)
*   [https://docs。甲骨文。com/javase/8/docs/API/Java/util/concurrent/priorityblockingqueue。html # to array-T:A-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/PriorityBlockingQueue.html#toArray-T:A-)