# Java 中的对象级锁定

> 原文:[https://www.geeksforgeeks.org/object-level-lock-in-java/](https://www.geeksforgeeks.org/object-level-lock-in-java/)

java 中的每个对象都有一个唯一的锁。每当我们使用同步关键字时，只有锁的概念会出现在图片中。如果线程想在给定对象上执行同步方法。首先，它必须获得该对象的锁。一旦线程获得了锁，那么它就被允许对该对象执行任何同步的方法。一旦方法执行完成，线程会自动释放锁。内部获取和释放锁由 JVM 负责，程序员不对这些活动负责

当我们希望同步一个非静态方法或非静态代码块时，对象级锁是一种机制，这样只有一个线程能够在类的给定实例上执行代码块。

如果线程想在给定对象上执行同步方法。首先，它必须获得该对象的锁。一旦线程获得了锁，那么它就被允许对该对象执行任何同步的方法。一旦方法执行完成，线程会自动释放锁。内部获取和释放锁由 JVM 负责，程序员不对这些活动负责。

**方法:**我们可以通过不同的方式将对象锁定在线程中，如下所示:

**方法 1:**

```
public class GeekClass
{
    public synchronized void GeekMethod(){}
}
```

**方法二:**

```
public class GeekClass
{
    public void GeekMethod(){
        synchronized (this)
        {
            // other thread safe code
        }
    }
}
```

**方法 3:**

```
public class DemoClass
{
    private final Object lock = new Object();
    public void demoMethod(){
        synchronized (lock)
        {
            // other thread safe code
        }
    }
}
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// Object lock concept

// Class
// Extending Runnable interface
class Geek implements Runnable {

    // Method of this class
    public void run() { Lock(); }

    // Synchronization of non-static methods
    // (object lock) as different synchronized
    // non-static methods are called in both threads

    // Then both threads need to acquire the object lock
    // After one is acquired, the other thread must wait
    // for one thread to finish the executing
    // before the other thread starts to execute.
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

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of above class
        // in the main() method
        Geek g = new Geek();

        // Sharing the same object across two Threads

        // Here, t1 takes g
        Thread t1 = new Thread(g);

        // Here, t2 takes g
        Thread t2 = new Thread(g);

        // Creating another object of above class
        Geek g1 = new Geek();

        // Here, t3 takes g1
        Thread t3 = new Thread(g1);

        // setname() method is used to change
        // name of the thread
        t1.setName("t1");
        t2.setName("t2");
        t3.setName("t3");

        // start() method beginning the execution of threads
        // as JVM calls the run() method of thread
        t1.start();
        t2.start();
        t3.start();
    }
}
```

**Output**

```
t1
t3
t2
in block t1
in block t3
in block t1 end
in block t2
in block t2 end
in block t3 end
```