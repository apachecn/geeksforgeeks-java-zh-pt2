# 在 Java 中，start()函数在多线程中做什么？

> 原文:[https://www . geesforgeks . org/start-function-多线程-java/](https://www.geeksforgeeks.org/start-function-multithreading-java/)

我们已经讨论过 [Java 线程通常使用两种方法之一来创建:(1)扩展线程类。(2)实现可运行的](https://www.geeksforgeeks.org/multithreading-in-java/)
在这两种方法中，我们覆盖了 run()函数，但是我们通过调用 start()函数来启动一个线程。那么我们为什么不直接调用 overridden run()函数呢？为什么总是调用 start 函数来执行线程？
**函数被调用时会发生什么？**
当调用一个函数时，会发生以下操作:

1.  参数被评估。
2.  新的堆栈帧被推入调用堆栈。
3.  参数已初始化。
4.  方法体被执行。
5.  值，并从调用堆栈中弹出当前堆栈帧。

**start()的目的是为线程创建一个单独的调用栈。它创建了一个单独的调用堆栈，然后 JVM 调用 run()。**
让我们看看如果不调用 start()而直接调用 run()会发生什么。我们已经修改了这里讨论的第一个程序。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to see that all threads are
// pushed on same stack if we use run()
// instead of start().
class ThreadTest extends Thread
{
  public void run()
  {
    try
    {
      // Displaying the thread that is running
      System.out.println ("Thread " +
                Thread.currentThread().getId() +
                " is running");

    }
    catch (Exception e)
    {
      // Throwing an exception
      System.out.println ("Exception is caught");
    }
  }
}

// Main Class
public class Main
{
  public static void main(String[] args)
  {
    int n = 8;
    for (int i=0; i<n; i++)
    {
      ThreadTest object = new ThreadTest();

      // start() is replaced with run() for
      // seeing the purpose of start
      object.run();
    }
  }
}
```

输出:

```java
Thread 1 is running
Thread 1 is running
Thread 1 is running
Thread 1 is running
Thread 1 is running
Thread 1 is running
Thread 1 is running
Thread 1 is running
```

我们可以从上面的输出中看到，我们得到了所有线程的相同 id，因为我们直接调用了 run()。调用 start()的程序打印不同的 id(见[本](https://ide.geeksforgeeks.org/UeWewe))
T3】参考:T5】

*   [http://www . javatpoint . com/what-if-we-call-run()-method-直接](http://www.javatpoint.com/what-if-we-call-run()-method-directly)
*   [http://www . LEEP point . net/JavaBasics/methods/methods-25-calls . html](http://www.leepoint.net/JavaBasics/methods/methods-25-calls.html)

本文由 **kp93** 投稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。