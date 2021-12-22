# Java 中的 PriorityBlockingQueue drainTo()方法

> 原文:[https://www . geeksforgeeks . org/priorityblockingqueue-drain to-method-in-Java/](https://www.geeksforgeeks.org/priorityblockingqueue-drainto-method-in-java/)

[PriorityBlockingQueue](https://www.geeksforgeeks.org/priorityblockingqueue-class-in-java/) 的 **drainTo(Collection col)** 方法从该 link edblockqueue 中移除所有可用元素，并将它们添加到作为参数传递的给定集合中。

### 排水(集合〔t0〕col)

**沥水(收藏<？super E > col)** 方法的 PriorityBlockingQueue 从这个队列中移除所有元素，并将它们添加到给定的集合 col 中。这是一种比重复轮询这个队列更有效的方法。

尝试从队列中向集合 c 添加元素时也可能遇到失败，并且由于该失败，当引发关联的异常时，元素会在两个集合之间分布。如果一个队列试图将 drainTo()排入队列本身，那么将引发 IllegalArgumentException。如果在操作过程中修改了指定的集合，则此操作的行为未定义。因此，为了使用这样的方法，需要注意这种类型的情况来克服异常。

**语法:**

```
public int drainTo(Collection<? super E> col)
```

**参数:**该方法接受一个参数**列**，表示从优先级阻塞队列传输元素的集合。

**返回值:**该方法返回从队列中排入集合的元素数量。

**异常:**该方法抛出以下异常:

*   **取消支持操作异常**–如果集合无法添加元素。
*   **class castexception**–如果元素的类停止了向集合中添加元素的方法。
*   **空指针异常**–如果集合为空
*   **IllegalArgumentException**–如果方法的参数阻止它被添加到指定的集合中

下面的程序说明了 PriorityBlockingQueue 类的 drainTo()方法:

**示例 1:** 程序演示 PriorityBlockingQueue 上的 drainTo()方法，该方法包含数组列表的数字列表。

```
// Java Program Demonstrate drainTo()
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

        // create a ArrayList of Integers
        ArrayList<Integer> list = new ArrayList<Integer>();

        // drain all elements of PriorityBlockingQueue to ArrayList
        // Using drainTo() method
        int noOfElementDrained = PrioQueue.drainTo(list);

        // print details
        System.out.println("No of elements drained :" + noOfElementDrained);
        System.out.println("ArrayList Contains element");

        for (int i : list)
            System.out.println(i);
    }
}
```

**Output:**

```
No of elements drained :6
ArrayList Contains element
5278367
7855642
35658786
74381793
76487590
87625142

```

**示例 2:**
下面的程序演示了 drainTo()方法引发的异常。

```
// Java Program Demonstrate drainTo()
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

        // create a collection with null
        ArrayList<String> collection = null;

        // try to drain to collection equals to null
        try {
            names.drainTo(collection);
        }
        catch (Exception e) {
            System.out.println("Exception Thrown: " + e);
        }
    }
}
```

**Output:**

```
Exception Thrown: java.lang.NullPointerException

```