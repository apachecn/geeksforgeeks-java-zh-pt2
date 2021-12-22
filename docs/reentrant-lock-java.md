# Java 中的重入锁

> 原文:[https://www.geeksforgeeks.org/reentrant-lock-java/](https://www.geeksforgeeks.org/reentrant-lock-java/)

**背景**

Java 中实现线程同步的传统方式是使用 [synchronized](https://www.geeksforgeeks.org/synchronized-in-java/) 关键字。虽然 synchronized 关键字提供了一定的基本同步，但它的使用非常严格。例如，一个线程只能获取一次锁。同步块不提供任何等待队列机制，在一个线程退出后，任何线程都可以获得锁。这可能会导致其他线程在很长一段时间内资源匮乏。
Java 中提供了重入锁，以提供更大灵活性的同步。

**什么是重入锁？**

可重入锁类实现锁接口，并在访问共享资源时提供方法同步。操纵共享资源的代码被对锁定和解锁方法的调用所包围。这将锁定当前工作线程，并阻止所有试图锁定共享资源的其他线程。

顾名思义，可重入锁允许线程多次进入资源锁。当线程第一次进入锁时，保持计数被设置为 1。在解锁之前，线程可以再次进入锁定状态，每次保持计数增加 1。对于每个解锁请求，保持计数递减 1，当保持计数为 0 时，资源解锁。

可重入锁还提供了一个公平性参数，通过该参数，锁将遵守锁请求的顺序，即在线程解锁资源后，锁将进入等待时间最长的线程。这种公平模式是通过将 true 传递给锁的构造函数来设置的。
这些锁的使用方式如下:

## Java 语言(一种计算机语言，尤用于创建网站)

```
public void some_method()
{
        reentrantlock.lock();
        try
        {
            //Do some work
        }
        catch(Exception e)
        {
            e.printStackTrace();
        }
        finally
        {
            reentrantlock.unlock();
        }

}
```

Unlock 语句总是在 finally 块中调用，以确保即使在方法体(try 块)中引发异常，锁也会被释放。

**重入锁()方法**

*   **lock():** 对 lock()方法的调用将保持计数增加 1，如果共享资源最初是空闲的，则将锁交给线程。
*   **unlock():** 对 unlock()方法的调用将保持计数递减 1。当这个计数达到零时，资源被释放。
*   **tryLock():** 如果资源没有被任何其他线程持有，那么对 tryLock()的调用返回 true，并且持有计数增加 1。如果资源没有空闲，那么方法返回 false，线程不会被阻塞，而是退出。
*   **tryLock(长超时，TimeUnit 单位):**按照方法，线程在退出之前会等待由方法的参数定义的某个时间段来获取资源上的锁。
*   **lock interruptible():**这个方法在获取资源时，如果资源空闲，同时允许线程被其他线程中断，则获取锁。这意味着，如果当前线程正在等待锁，但其他一些线程请求锁，那么当前线程将被中断并立即返回，而不获取锁。
*   **getHoldCount():** 此方法返回资源上持有的锁数的计数。
*   **isHeldByCurrentThread():** 如果资源上的锁由当前线程持有，则此方法返回 true。

**重入锁()示例**

在下面的教程中，我们将看一个可重入锁的基本例子。

**应遵循的步骤**

```
1\. Create an object of ReentrantLock
2\. Create a worker(Runnable Object) to execute and pass the lock to the object
3\. Use the lock() method to acquire the lock on shared resource
4\. After completing work, call unlock() method to release the lock 
```

下面是问题陈述的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate Reentrant Locks
import java.text.SimpleDateFormat;
import java.util.Date;
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;
import java.util.concurrent.locks.ReentrantLock;

class worker implements Runnable
{
  String name;
  ReentrantLock re;
  public worker(ReentrantLock rl, String n)
  {
    re = rl;
    name = n;
  }
  public void run()
  {
    boolean done = false;
    while (!done)
    {
      //Getting Outer Lock
      boolean ans = re.tryLock();

      // Returns True if lock is free
      if(ans)
      {
        try
        {
          Date d = new Date();
          SimpleDateFormat ft = new SimpleDateFormat("hh:mm:ss");
          System.out.println("task name - "+ name
                     + " outer lock acquired at "
                     + ft.format(d)
                     + " Doing outer work");
          Thread.sleep(1500);

          // Getting Inner Lock
          re.lock();
          try
          {
            d = new Date();
            ft = new SimpleDateFormat("hh:mm:ss");
            System.out.println("task name - "+ name
                       + " inner lock acquired at "
                       + ft.format(d)
                       + " Doing inner work");
            System.out.println("Lock Hold Count - "+ re.getHoldCount());
            Thread.sleep(1500);
          }
          catch(InterruptedException e)
          {
            e.printStackTrace();
          }
          finally
          {
            //Inner lock release
            System.out.println("task name - " + name +
                       " releasing inner lock");

            re.unlock();
          }
          System.out.println("Lock Hold Count - " + re.getHoldCount());
          System.out.println("task name - " + name + " work done");

          done = true;
        }
        catch(InterruptedException e)
        {
          e.printStackTrace();
        }
        finally
        {
          //Outer lock release
          System.out.println("task name - " + name +
                     " releasing outer lock");

          re.unlock();
          System.out.println("Lock Hold Count - " +
                       re.getHoldCount());
        }
      }
      else
      {
        System.out.println("task name - " + name +
                      " waiting for lock");
        try
        {
          Thread.sleep(1000);
        }
        catch(InterruptedException e)
        {
          e.printStackTrace();
        }
      }
    }
  }
}

public class test
{
  static final int MAX_T = 2;
  public static void main(String[] args)
  {
    ReentrantLock rel = new ReentrantLock();
    ExecutorService pool = Executors.newFixedThreadPool(MAX_T);
    Runnable w1 = new worker(rel, "Job1");
    Runnable w2 = new worker(rel, "Job2");
    Runnable w3 = new worker(rel, "Job3");
    Runnable w4 = new worker(rel, "Job4");
    pool.execute(w1);
    pool.execute(w2);
    pool.execute(w3);
    pool.execute(w4);
    pool.shutdown();
  }
}
```

**样品执行**

```
Output:
task name - Job2 waiting for lock
task name - Job1 outer lock acquired at 09:49:42 Doing outer work
task name - Job2 waiting for lock
task name - Job1 inner lock acquired at 09:49:44 Doing inner work
Lock Hold Count - 2
task name - Job2 waiting for lock
task name - Job2 waiting for lock
task name - Job1 releasing inner lock
Lock Hold Count - 1
task name - Job1 work done
task name - Job1 releasing outer lock
Lock Hold Count - 0
task name - Job3 outer lock acquired at 09:49:45 Doing outer work
task name - Job2 waiting for lock
task name - Job3 inner lock acquired at 09:49:47 Doing inner work
Lock Hold Count - 2
task name - Job2 waiting for lock
task name - Job2 waiting for lock
task name - Job3 releasing inner lock
Lock Hold Count - 1
task name - Job3 work done
task name - Job3 releasing outer lock
Lock Hold Count - 0
task name - Job4 outer lock acquired at 09:49:48 Doing outer work
task name - Job2 waiting for lock
task name - Job4 inner lock acquired at 09:49:50 Doing inner work
Lock Hold Count - 2
task name - Job2 waiting for lock
task name - Job2 waiting for lock
task name - Job4 releasing inner lock
Lock Hold Count - 1
task name - Job4 work done
task name - Job4 releasing outer lock
Lock Hold Count - 0
task name - Job2 outer lock acquired at 09:49:52 Doing outer work
task name - Job2 inner lock acquired at 09:49:53 Doing inner work
Lock Hold Count - 2
task name - Job2 releasing inner lock
Lock Hold Count - 1
task name - Job2 work done
task name - Job2 releasing outer lock
Lock Hold Count - 0
```

**要点**

1.  人们可能会忘记在 finally 块中调用 unlock()方法，从而导致程序中出现错误。确保在线程退出之前释放锁。
2.  用于构造锁对象的公平性参数降低了程序的吞吐量。

可重入锁是同步的更好替代，它提供了许多同步所没有的特性。然而，这些显而易见的好处的存在并不是一个足够好的理由来总是喜欢重入锁来同步。相反，根据您是否需要可重入锁提供的灵活性来做出决定。

本文由 **Abhishek** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。