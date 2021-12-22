# Java 中并发集合的需求

> 原文:[https://www . geesforgeks . org/need-concurrent-collections-Java/](https://www.geeksforgeeks.org/need-concurrent-collections-java/)

正如我们已经知道的[集合](https://www.geeksforgeeks.org/collections-in-java-2/)只不过是对象的集合，在这里我们使用一些预定义的方法来处理对象。但是当我们在多线程中使用集合概念时，会出现几个问题。在多线程应用程序中使用集合时出现的问题:

*   大多数集合类对象(如[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)、[链接列表](https://www.geeksforgeeks.org/linked-list-in-java/)、[哈希映射](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)等)本质上是非同步的，即多个线程可以同时在一个对象上执行。因此，对象不是线程安全的。
*   很少有类对象(如[向量](https://www.geeksforgeeks.org/java-util-vector-class-java/)、[堆栈](https://www.geeksforgeeks.org/stack-class-in-java/)、[哈希表](https://www.geeksforgeeks.org/java-util-hashtable-class-java/))在本质上是同步的，即一次只有一个线程可以在一个对象上执行。但是这里的问题是性能很低，因为一次只有一个线程执行一个对象，其余的线程必须等待。
*   主要问题是当一个线程迭代一个 Collections 对象时，如果另一个线程不能修改该对象的内容。如果另一个线程试图修改对象的内容，那么我们会得到一个运行时异常，表示 ConcurrentModificationException。
*   由于上述原因，Collections 类不适合或者我们可以说是多线程应用程序的好选择。

为了克服上述问题，SUN 微系统在 JDK 1.5 版本中引入了一个新特性，它就是并发集合。

```java
// Java program to illustrate Concurrent
// Collection need
import java.util.*;
class ConcurrentDemo extends Thread {
    static ArrayList l = new ArrayList();
    public void run()
    {
        try {
            Thread.sleep(2000);
        }
        catch (InterruptedException e) {
            System.out.println("Child Thread" + 
                      " going to add element");
        }

        // Child thread trying to add new
        // element in the Collection object
        l.add("D");
    }

    public static void main(String[] args) 
                   throws InterruptedException
    {
        l.add("A");
        l.add("B");
        l.add("c");

        // We create a child thread that is 
        // going to modify ArrayList l.
        ConcurrentDemo t = new ConcurrentDemo();
        t.start();

        // Now we iterate through the ArrayList
        // and get exception.
        Iterator itr = l.iterator();
        while (itr.hasNext()) {
            String s = (String)itr.next();
            System.out.println(s);
            Thread.sleep(6000);
        }
        System.out.println(l);
    }
}
```

输出:

线程“主”出现异常