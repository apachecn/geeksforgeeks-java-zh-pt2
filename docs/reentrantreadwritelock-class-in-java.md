# 在 Java 中重新输入读写锁类

> 原文:[https://www . geeksforgeeks . org/re entrantreadwritellock-class-in-Java/](https://www.geeksforgeeks.org/reentrantreadwritelock-class-in-java/)

**Java 的可重入读写锁**类是读写锁的实现，也支持可重入锁功能。

读写锁是一对关联的锁，一个用于只读操作，一个用于写操作。然而，可重入锁是一种可重入互斥锁，其行为与使用同步方法和语句访问的隐式监视器锁相同，但具有一些更扩展的功能。

**Java 中的读写锁**

即使在多线程应用程序中，共享资源也可能同时发生多次读取。只有当多个写入同时发生或读写混合时，才有可能写入错误的值或读取错误的值。

Java 中的读写锁使用相同的思想，通过拥有独立的锁对来提高性能。读写锁维护一对关联的锁-

1.  一个用于只读操作；和
2.  一个写的。

只要没有写线程，读锁就可以由多个读线程同时持有。写锁是独占的。

拥有一对[读写锁](https://www.geeksforgeeks.org/readwritelock-interface-in-java/)允许在访问共享数据时比互斥锁允许的并发级别更高。它利用了这样一个事实，即虽然一次只有一个线程(写线程)可以修改共享数据，但在许多情况下，任何数量的线程都可以并发读取数据(因此读线程)。

如果读操作的频率大于写操作的频率，读操作的持续时间大于写操作的持续时间，读写锁将比互斥锁的使用提高性能。这还取决于对数据的争用，也就是说，试图同时读取或写入数据的线程数量。

包资源管理器视图

```
• java.lang.Object
    • java.util.concurrent.locks.ReentrantReadWriteLock
```

**语法:**导入类

```
public class ReentrantReadWriteLock
extends Object
implements ReadWriteLock, Serializable
```

**建造师总结**

1.  可重入读写锁():使用默认(非空)排序属性创建一个新的可重入读写锁。
2.  可重入读写锁(布尔公平):用给定的公平策略创建一个新的可重入读写锁。

引发异常:

*   [空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/):如果锁为空

**实施:**

我们将创建三个可运行的实现。它们都使用可重入读写锁变量。锁是使用可重入读写锁(布尔公平)构造函数创建的，因此它有一个公平策略:

*   里德拿到了锁。它使用可重入读写锁的读锁()方法来获取读锁。然后，它使用 read lock 的 lock()方法获取读锁。拥有锁时，它读取字符串消息变量的值。然后，它尝试使用 ReadLock 的 unlock()方法释放锁。
*   WriteA 和 WriteB 也获得锁，使用 writeLock()方法，返回一个 WriteLock，然后使用 WriteLock 的 unlock()方法。由于拥有写锁，它们都改变了字符串消息变量的值。然后，他们使用 write lock 的 unlock()方法释放写锁。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate ReentrantReadWriteLock Class

// Importing ReentrantReadWriteLock
// fro java.util package
import java.util.concurrent.locks.ReentrantReadWriteLock;

// Class 1
// Main class
public class ReentrantReadWriteLockExample {

    private static final ReentrantReadWriteLock lock
        = new ReentrantReadWriteLock(true);

    // Initially the string contains only 1 character
    private static String message = "a";

    // Main driver method
    public static void main(String[] args)
        throws InterruptedException
    {

        // Creating threads
        Thread t1 = new Thread(new Read());
        Thread t2 = new Thread(new WriteA());
        Thread t3 = new Thread(new WriteB());

        // Starting threads with help of start() method
        t1.start();
        t2.start();
        t3.start();
        t1.join();
        t2.join();
        t3.join();
    }

    // Class 2
    // Helper class implementig Runnable interface
    static class Read implements Runnable {

        // run() method for thread
        public void run()
        {

            for (int i = 0; i <= 10; i++) {
                if (lock.isWriteLocked()) {
                    System.out.println(
                        "I'll take the lock from Write");
                }

                // operating lock()
                lock.readLock().lock();

                System.out.println(
                    "ReadThread "
                    + Thread.currentThread().getId()
                    + "Message is " + message);
                lock.readLock().unlock();
            }
        }
    }

    // Class 3
    // Helper class implementig Runnable interface
    static class WriteA implements Runnable {

        // run() method for thread
        public void run()
        {

            for (int i = 0; i <= 10; i++) {

                // Try block to check fr exceptions
                try {
                    lock.writeLock().lock();
                    message = message.concat("a");
                }
                finally {
                    lock.writeLock().unlock();
                }
            }
        }
    }

    // Class 4
    // Helper class implementig Runnable interface
    static class WriteB implements Runnable {

        // run() method for thread
        public void run()
        {

            for (int i = 0; i <= 10; i++) {

                // Try block to check for exceptions
                try {
                    lock.writeLock().lock();
                    message = message.concat("b");
                }
                finally {
                    lock.writeLock().unlock();
                }
            }
        }
    }
}
```

**Output**

```
ReadThread 11 ---> Message is a
ReadThread 11 ---> Message is aba
ReadThread 11 ---> Message is ababa
ReadThread 11 ---> Message is abababa
ReadThread 11 ---> Message is ababababa
ReadThread 11 ---> Message is abababababa
ReadThread 11 ---> Message is ababababababa
ReadThread 11 ---> Message is abababababababa
ReadThread 11 ---> Message is ababababababababa
ReadThread 11 ---> Message is abababababababababa
ReadThread 11 ---> Message is ababababababababababa
```