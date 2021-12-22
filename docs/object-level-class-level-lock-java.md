# Java 中的对象级和类级锁

> 原文:[https://www . geesforgeks . org/object-level-class-level-lock-Java/](https://www.geeksforgeeks.org/object-level-class-level-lock-java/)

**同步:**

[同步](https://www.geeksforgeeks.org/synchronized-in-java/)是仅用于方法和块的修改器。在同步修饰符的帮助下，我们可以限制共享资源只能被一个线程访问。当两个或多个线程需要访问共享资源时，会有一些数据丢失，即数据不一致。我们可以在多个线程之间实现数据一致性的过程称为同步。

**为什么需要同步？**

让我们假设您有两个线程正在读取和写入同一个“资源”。假设有一个名为 geek 的变量，您希望一次只有一个线程可以访问该变量(原子方式)。但是如果没有 synchronized 关键字，线程 1 可能看不到线程 2 对 geek 所做的更改，或者更糟的是，可能只有一半的更改会导致数据不一致的问题。这不是你逻辑上所期望的。防止这些错误所需的工具是同步。

**在同步中，线程上有两种锁:**

*   **对象级锁:**Java 中的每个对象都有一个唯一的锁。每当我们使用同步关键字时，只有锁的概念会出现在图片中。如果一个线程想要在给定的对象上执行同步方法。首先，它必须锁定该对象。一旦线程获得了锁，那么它就被允许对该对象执行任何同步的方法。一旦方法执行完成，线程会自动释放锁。内部获取和释放锁由 JVM 负责，程序员不对这些活动负责。让我们看看下面的程序，了解对象级锁定:

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate
// Object lock concept
class Geek implements Runnable {
    public void run() { Lock(); }
    public void Lock()
    {
        System.out.println(
            Thread.currentThread().getName());
        synchronized (this)
        {
            System.out.println(
                "in block "
                + Thread.currentThread().getName());
            System.out.println(
                "in block "
                + Thread.currentThread().getName()
                + " end");
        }
    }

    public static void main(String[] args)
    {
        Geek g = new Geek();
        Thread t1 = new Thread(g);
        Thread t2 = new Thread(g);
        Geek g1 = new Geek();
        Thread t3 = new Thread(g1);
        t1.setName("t1");
        t2.setName("t2");
        t3.setName("t3");
        t1.start();
        t2.start();
        t3.start();
    }
}
```

**Output**

```java
t1
t3
t2
in block t3
in block t1
in block t3 end
in block t1 end
in block t2
in block t2 end

```

*   **类级锁:**Java 中的每个类都有一个唯一的锁，这个锁只不过是类级锁。如果一个线程想要执行一个静态同步方法，那么这个线程需要一个类级锁。一旦线程获得了类级别的锁，那么它就被允许执行该类的任何静态同步方法。一旦方法执行完成，线程会自动释放锁。让我们看看下面的程序，以便更好地理解:

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate class level lock
class Geek implements Runnable {
    public void run() { Lock(); }

    public void Lock()
    {
        System.out.println(
            Thread.currentThread().getName());
        synchronized (Geek.class)
        {
            System.out.println(
                "in block "
                + Thread.currentThread().getName());
            System.out.println(
                "in block "
                + Thread.currentThread().getName()
                + " end");
        }
    }

    public static void main(String[] args)
    {
        Geek g1 = new Geek();
        Thread t1 = new Thread(g1);
        Thread t2 = new Thread(g1);
        Geek g2 = new Geek();
        Thread t3 = new Thread(g2);
        t1.setName("t1");
        t2.setName("t2");
        t3.setName("t3");
        t1.start();
        t2.start();
        t3.start();
    }
}
```

**Output**

```java
t1
t2
t3
in block t1
in block t1 end
in block t3
in block t3 end
in block t2
in block t2 end

```

**参考:**[https://docs . Oracle . com/javase/tutorial/essential/concurrency/sync . html](https://docs.oracle.com/javase/tutorial/essential/concurrency/sync.html)

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。