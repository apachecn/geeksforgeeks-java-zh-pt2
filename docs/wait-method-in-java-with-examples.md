# Java 中的 wait()方法示例

> 原文:[https://www . geesforgeks . org/wait-method-in-Java-with-examples/](https://www.geeksforgeeks.org/wait-method-in-java-with-examples/)

[线程间通信](https://www.geeksforgeeks.org/inter-thread-communication-java/)是一种同步线程可以使用等待()和通知()方法相互通信的方式。wait()方法是 java.lang.Object 类的一部分。当 wait()方法被调用时，调用线程停止执行，直到 notify()或 notifyAll()方法被其他线程调用。

**语法:**

```
public final void wait() throws InterruptedException
```

**异常**

*   [中断异常](https://docs.oracle.com/javase/7/docs/api/java/lang/InterruptedException.html)–如果任何线程在当前线程等待通知之前或期间中断了当前线程。
*   [illegalMonitorStateException](https://docs.oracle.com/javase/7/docs/api/java/lang/IllegalMonitorStateException.html)–如果当前线程不是对象监视器的所有者。

**工作:**

*   在 java 中，同步的方法和块一次只允许一个线程获取资源锁。因此，当线程调用 wait()方法时，它会放弃对该资源的锁定并进入睡眠状态，直到其他线程进入同一监视器并调用 notify()或 notifyAll()方法。
*   调用 notify()只会唤醒一个线程，而调用 notifyAll()会唤醒同一对象上的所有线程。调用这两个方法并不会放弃对资源的锁定，相反，它的工作是使用 wait()方法唤醒已经被发送到睡眠状态的线程。
*   sleep()方法和 wait()方法的一个很大区别是，sleep()方法使线程休眠指定的时间，而 wait()方法使线程休眠，直到调用 notifyAll()和 notifyAll()为止。

在下面提到的代码中，我们创建了一个类**枪战**，它包含一个初始化为 40 的成员变量子弹和两个方法 fire()和 reload()。fire()方法激发传递给它的项目符号数，直到项目符号变为 0，当项目符号变为 0 时，它调用 wait()方法，该方法使调用线程休眠并释放对象上的锁，而 reload()方法将项目符号增加 40，并调用 notify()方法，该方法唤醒等待的线程。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the use of wait() method
class GunFight {
    private int bullets = 40;

    // This method fires the number of bullets that are
    // passed it. When the bullet in magazine becomes zero,
    // it calls the wait() method and releases the lock.
    synchronized public void fire(int bulletsToBeFired)
    {
        for (int i = 1; i <= bulletsToBeFired; i++) {
            if (bullets == 0) {
                System.out.println(i - 1
                                   + " bullets fired and "
                                   + bullets + " remains");
                System.out.println(
                    "Invoking the wait() method");
                try {
                    wait();
                }
                catch (InterruptedException e) {
                    e.printStackTrace();
                }
                System.out.println(
                    "Continuing the fire after reloading");
            }

            bullets--;
        }
        System.out.println(
            "The firing process is complete");
    }

    // reload() increases the bullets by 40 everytime it is
    // invoked and calls the notify() method which wakes up
    // the thread that was sent to sleep using wait() inside
    // of fire() method
    synchronized public void reload()
    {
        System.out.println(
            "Reloading the magazine and resuming "
            + "the thread using notify()");
        bullets += 40;
        notify();
    }
}

public class WaitDemo extends Thread {
    public static void main(String[] args)
    {

        GunFight gf = new GunFight();

        // Creating a new thread and invoking
        // our fire() method on it
        new Thread() {
            @Override public void run() { gf.fire(60); }
        }.start();

        // Creating a new thread and invoking
        // our reload method on it
        new Thread() {
            @Override public void run() { gf.reload(); }
        }.start();
    }
}
```

**Output**

```
40 bullets fired and 0 remains
Invoking the wait() method
Reloading the magazine and resuming the thread using notify()
Continuing the fire after reloading
The firing process is complete
```