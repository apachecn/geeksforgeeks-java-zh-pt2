# 为什么在 JDK 1.1 版本之后，Thread.stop()、Thread.suspend()和 Thread.resume()方法被弃用？

> 原文:[https://www . geesforgeks . org/why-thread-stop-thread-suspend-thread-resume-methods-after-JDK-1-1-version/](https://www.geeksforgeeks.org/why-thread-stop-thread-suspend-and-thread-resume-methods-are-deprecated-after-jdk-1-1-version/)

Thread 类包含用于创建和操作线程的构造函数和方法。线程是实现可运行接口的对象的子类。线程类中有很多方法，但是从 JDK 1.1 开始，其中一些方法被弃用了。在本文中，我们将了解其背后的原因。

不推荐使用的方法不再被认为是重要的，不应该使用，因为它们可能会从类中移除。类随着时间的推移而演变，导致它们的 API 改变，从而导致贬值。属性改变，方法被重命名，新的方法被添加。为了帮助开发人员从旧的应用编程接口转换到新的应用编程接口，不推荐使用的类和方法在文档注释中被标记为@不推荐使用。

**为什么不推荐使用？？**

**Thread.stop()** 由于其固有的风险，正在被逐步淘汰。当你停止一个线程时，它会解锁它锁定的所有监视器。如果先前受这些监视器保护的任何对象处于不一致状态，其他线程可能会看到这些对象处于不一致状态。
作用在受损物体上的线可以不规则地运动，不管是有意识的还是无意识的。ThreadDeath 与其他不受控制的异常不同，它以静默方式杀死线程，不会给用户留下程序可能被破坏的警告。损害发生后，腐败可能会在不可预见的时刻出现。此外，在多线程环境中使用 DBMS-JDBC 时，杀死一个线程会产生问题。

**Thread.suspend()** 不推荐使用，因为它本身就容易出现死锁。因此， **Thread.resume()** 也必须弃用。当目标线程被挂起时，它在监视器上持有一个锁，保护一个关键的系统资源，并且在目标线程被恢复之前，没有其他线程可以访问它。如果将重新启动目标线程的线程在调用 resume()之前试图锁定此监视器，则会发生死锁。

使用这些不推荐使用的方法可能导致死锁的示例:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// This class contains an integer array &
// Threads set the element's value for this array
class NumVal {
    private int num[] = null;
    boolean valueSet = false;
    int i = 0;
    NumVal()
    {
        // Creating integer array of 10 elements
        num = new int[10];
    }
    // method to set the values in the array
    public void setVal(int n)
    {
        if (i < 9) {
            System.out.println("Putting value " + n
                               + " in the NumVal Array");
            num[i] = n;
            i++;
        }
    }
    // method to get the values from the array
    public int getVal()
    {
        if (i >= 0) {

            System.out.println("Giving n = " + num[i]);
            i--;
            return num[i + 1];
        }
        else {
            return -1;
        }
    }
}
// Creating Our Thread Class
class MyThread extends Thread {

    // MyThread want mutually exclusive
    // lock on the object
    // referred by: NumObjToSetVal
    NumVal NumObjToSetVal = null;

    // Constructor
    public MyThread(String threadName, NumVal numV)
    {
        super(threadName);
        NumObjToSetVal = numV;
    }

    public void run()
    {
        // Only 1 thread at a time an access the object
        // referred by : NumObjToSetVal
        synchronized (NumObjToSetVal)
        {
            int n = 0;
            while (n < 5) {
                System.out.println(
                    "THREAD NAME : "
                    + Thread.currentThread().getName());
                n++;
                NumObjToSetVal.setVal(n);
                try {
                    // Make the thread sleep for 100 ms
                    Thread.sleep(100);
                    System.out.println(
                        Thread.currentThread().getName()
                        + "is awake now");
                }
                catch (Exception e) {
                    System.out.println("Exception Caught");
                }
                // If n is 2 , we suspend this thread
                if (n == 2) {
                    // suspend the thread, now this thread
                    // will release lock on NumObjToSetVal
                    // only when resume() method is called
                    // on this thread, thread will go in
                    // waiting state
                    Thread.currentThread().suspend();
                }
            }
        }
    }
}

public class Main {
    public static void main(String[] args)
    {
        // TODO Auto-generated method stub
        NumVal v = new NumVal();

        // Creating thread 1 that want exclusive lock on
        // object referred by v
        MyThread thread1 = new MyThread("Thread1 ", v);

        // Creating thread 2 that want exclusive lock on
        // object referred by v
        // thread1 is not going to release lock on Object
        // referred by v until resume() method is not called
        // and for acquiring lock on v Object refred by v ,
        // thread1 must have released lock on Object
        // referred by v, if lock is not released, thread2
        // will keep on waiting for thread1 to release lock
        // onbject referred by v & deadlock will be formed
        MyThread thread2 = new MyThread("Thread2 ", v);

        // starting both threads
        thread1.start();
        thread2.start();

        for (int i = 500; i <= 501; i++) {
            System.out.println("Main Thread " + i);
        }
    }
}
```

**输出:**

```
THREAD NAME : Thread1 
Putting value 1 in the NumVal Array
Main Thread 500
Main Thread 501
Thread1 is awake now
THREAD NAME : Thread1 
Putting value 2 in the NumVal Array
Thread1 is awake now
//Deadlock is created & hence no output after this
```

**说明:**我们创建了 2 个线程:线程 1 &线程 2。两者都希望获得“v”引用所引用的 NumVal 对象的锁。

当我们通过调用 start()方法启动两个线程时，每当线程获得 CPU 时，run()方法就会执行。Thread1 获取 CPU &当在其运行方法中 n 的值为 2 时，线程被挂起。线程 1 不会释放对“v”引用的对象的锁定，直到对其调用 resume()为止。

要让线程 2 获得“v”所指的 v 对象上的锁，线程 1 必须已经释放了“v”所指的对象上的锁。这里的锁没有被释放，thread2 将继续等待 thread1 释放被“v”引用的对象上的锁&将形成死锁。

因此，每当您在同一个线程上调用 suspend()方法时，您总是在该线程上调用 resume()。