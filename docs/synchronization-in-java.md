# Java 中的同步

> 原文:[https://www.geeksforgeeks.org/synchronization-in-java/](https://www.geeksforgeeks.org/synchronization-in-java/)

[多线程](https://www.geeksforgeeks.org/multithreading-in-java/)程序可能经常会出现多个线程试图访问相同资源，最终产生错误和不可预见的结果的情况。

因此，需要通过某种同步方法来确保在给定的时间点只有一个线程可以访问资源。Java 提供了一种使用同步块创建线程并同步其任务的方法。Java 中的同步块用 Synchronized 关键字标记。Java 中的同步块是在某个对象上同步的。在同一对象上同步的所有同步块一次只能有一个线程在其中执行。所有试图进入同步块的其他线程都被阻塞，直到同步块内的线程退出该块。

以下是同步块的一般形式:

```java
// Only one thread can execute at a time. 
// sync_object is a reference to an object
// whose lock associates with the monitor. 
// The code is said to be synchronized on
// the monitor object
synchronized(sync_object)
{
   // Access shared variables and other
   // shared resources
}
```

这种同步是用一个叫做监视器的概念在 Java 中实现的。在给定时间，只有一个线程可以拥有一个监视器。当一个线程获得一个锁时，它就被称为进入了监视器。所有试图进入锁定监视器的其他线程将被挂起，直到第一个线程退出监视器。

下面是一个多线程同步的例子。

## 爪哇

```java
// A Java program to demonstrate working of
// synchronized.

import java.io.*;
import java.util.*;

// A Class used to send a message
class Sender
{
    public void send(String msg)
    {
        System.out.println("Sending\t"  + msg );
        try
        {
            Thread.sleep(1000);
        }
        catch (Exception e)
        {
            System.out.println("Thread  interrupted.");
        }
        System.out.println("\n" + msg + "Sent");
    }
}

// Class for send a message using Threads
class ThreadedSend extends Thread
{
    private String msg;
    Sender  sender;

    // Receives a message object and a string
    // message to be sent
    ThreadedSend(String m,  Sender obj)
    {
        msg = m;
        sender = obj;
    }

    public void run()
    {
        // Only one thread can send a message
        // at a time.
        synchronized(sender)
        {
            // synchronizing the snd object
            sender.send(msg);
        }
    }
}

// Driver class
class SyncDemo
{
    public static void main(String args[])
    {
        Sender snd = new Sender();
        ThreadedSend S1 =
            new ThreadedSend( " Hi " , snd );
        ThreadedSend S2 =
            new ThreadedSend( " Bye " , snd );

        // Start two threads of ThreadedSend type
        S1.start();
        S2.start();

        // wait for threads to end
        try
        {
            S1.join();
            S2.join();
        }
        catch(Exception e)
        {
            System.out.println("Interrupted");
        }
    }
}
```

**输出**

```java
Sending     Hi 

 Hi Sent
Sending     Bye 

 Bye Sent
```

每次运行程序，输出都是一样的。

在上面的例子中，我们选择在 ThreadedSend 类的 run()方法中同步 Sender 对象。或者，我们可以将**整个发送()块定义为同步的**、，产生相同的结果。那么我们就不需要在 ThreadedSend 类的 run()方法中同步 Message 对象。

```java
// An alternate implementation to demonstrate
// that we can use synchronized with method also.

class Sender {
   public synchronized void send(String msg)
   {
       System.out.println("Sending\t" + msg);
       try {
           Thread.sleep(1000);
       }
       catch (Exception e) {
           System.out.println("Thread interrupted.");
       }
       System.out.println("\n" + msg + "Sent");
   }
}
```

我们不必总是同步整个方法。有时最好只同步方法的一部分。方法内部的 Java 同步块使这成为可能。

```java
// One more alternate implementation to demonstrate
// that synchronized can be used with only a part of  
// method

class Sender  
{
   public void send(String msg)
   {
       synchronized(this)
       {
           System.out.println("Sending\t" + msg );
           try  
           {
               Thread.sleep(1000);
           }  
           catch (Exception e)  
           {
               System.out.println("Thread interrupted.");
           }
           System.out.println("\n" + msg + "Sent");
       }
   }
}
```

本文由 **Souradeep Barua** 供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论