# 在 Java 线程中使用阻塞队列的生产者消费者解决方案

> 原文:[https://www . geesforgeks . org/producer-consumer-solution-use-blocking queue-in-Java-thread/](https://www.geeksforgeeks.org/producer-consumer-solution-using-blockingqueue-in-java-thread/)

**生产者-消费者**问题是一个 [**同步**](https://www.geeksforgeeks.org/synchronized-in-java/) 问题，当一个或多个线程生成数据，并将其放在一个缓冲区中，同时一个或多个线程从同一缓冲区中消费数据时，就会出现这个问题。

这样做可能会导致**竞争状态**，其中线程相互竞争以完成它们的任务。在这种情况下，没有什么可以阻止他们同时输入方法并产生错误的结果。

此外，由于缺乏**线程间通信**，即使缓冲区为空，消费者也可能试图移除元素。同样，当缓冲区已满时，生成器可能会尝试添加一个元素。

**可能的解决方案:**

1.  **在移除和添加之前检查缓冲区的大小**似乎是一个解决方案。生产者-消费者系统通常使用无限 while 循环。检查循环每次迭代的大小是低效的。此外，线程安全也无法得到保证。因此，不使用该解决方案。
2.  [**等待()&通知()**可以使用](https://www.geeksforgeeks.org/producer-consumer-solution-using-threads-java/)方法建立线程间通信。
3.  **BlockingQueue** 是比 wait() & notify()更简单的线程安全替代方案。本文讨论了这种方法。

**封锁队列:**

[阻塞队列接口](https://www.geeksforgeeks.org/blockingqueue-interface-in-java/)是 java.util.concurrent 包的一部分。

*   如果一个生产者线程试图将一个元素放入一个完整的阻塞队列中，它会被阻塞并保持阻塞，直到消费者移除一个元素。
*   类似地，如果一个使用者线程试图从一个空的阻塞队列中获取一个元素，它会被阻塞并保持阻塞，直到生产者添加一个元素。

**BlockingQueue 有两种主要方法**，即 put()和 take()

**put()**

> 空放(E)抛出中断异常
> 
> e 是要添加的元素
> 中断如果线程在等待时被中断，将引发异常

**取()**

> E take()引发中断异常
> 
> 返回队列头
> 中断如果线程在等待时被中断，将引发异常

封锁队列也有**添加(E e)** 和**移除()**的方法。但是这些方法不能用于生产者-消费者问题，因为:

*   如果队列已满，add 将引发 IllegalStateException。
*   remove 返回一个布尔值，但要返回一个元素。

### 阻塞队列的实现

因为阻塞队列是一个接口，所以我们不能创建它的对象。相反，我们可以创建一个实现阻塞队列的类的对象。对于本演示，应使用 ArrayBlockingQueue。

**数组块队列**

*   顾名思义，ArrayBlockingQueue 使用数组数据结构作为缓冲区。
*   因为它是一个数组，所以它的容量在声明后是固定的。
*   它将公平作为一种选择。这意味着线程可以在先到先得的基础上访问缓冲区。默认情况下，公平是关闭的。可以通过将布尔值 true 放在构造函数中来打开它。

### 生产-消费者解决方案

现在我们了解了什么是阻塞队列及其用法。让我们运用这些知识来解决生产者-消费者问题。为了方便起见，我们可以通过为生产者和消费者创建一个单独的类，将这个问题分成两个子问题。生产者和消费者将由不同的线程操作，但将共享一个公共的阻塞队列缓冲区。

**生产者:**顾名思义，生产者类将产生数据。在我们的例子中，生产者类产生范围为[1，4]的数字。它会将这些数据放入阻塞队列缓冲区。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate producer code

// Implement Runnable since object
// of this class will be executed by
// a separate thread
class producer implements Runnable {

    BlockingQueue<Integer> obj;

    public producer(BlockingQueue<Integer> obj)
    {
        // accept an ArrayBlockingQueue object from
        // constructor
        this.obj = obj;
    }

    @Override public void run()
    {

         // Produce numbers in the range [1,4]
         // and put them in the buffer
        for (int i = 1; i <= 4; i++) {
            try {
                obj.put(i);
                System.out.println("Produced " + i);
            }
            catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}
```

**消费者:**消费者将从阻塞队列缓冲区获取数据。在我们的例子中，这些数据将被简单地打印出来。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate consumer code

// Implement Runnable since object
// of this class will be executed by
// a separate thread
class consumer implements Runnable {

    BlockingQueue<Integer> obj;

    // Initialize taken to -1
    // to indicate that no number
    // has been taken so far.
    int taken = -1;

    public consumer(BlockingQueue<Integer> obj)
    {
        // accept an ArrayBlockingQueue object from
        // constructor
        this.obj = obj;
    }

    @Override public void run()
    {

        // Take numbers from the buffer and
        // print them, if the last number taken
        // is 4 then stop
        while (taken != 4) {
            try {
                taken = obj.take();
                System.out.println("Consumed " + taken);
            }
            catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}
```

现在让我们创建一个 ArrayBlockingQueue 缓冲区对象，生产者和消费者各有一个线程，然后执行解决方案。

**生产者-消费者问题解决方案:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate producer consumer
// problem solution

// Import the BlockingQueue interface and
// ArrayBlockingQueue class
import java.util.concurrent.ArrayBlockingQueue;
import java.util.concurrent.BlockingQueue;

// Create a Main class for execution
public class Main {
    public static void main(String[] args)
    {

        // Create an ArrayBlockingQueue object with capacity
        // 4
        BlockingQueue<Integer> bqueue
            = new ArrayBlockingQueue<Integer>(4);

        // Create 1 object each for producer
        // and consumer and pass them the common
        // buffer created above
        producer p1 = new producer(bqueue);
        consumer c1 = new consumer(bqueue);

        // Create 1 thread each for producer
        // and consumer and pass them their
        // respective objects.
        Thread pThread = new Thread(p1);
        Thread cThread = new Thread(c1);

        // Start both threads
        pThread.start();
        cThread.start();
    }
}

class producer implements Runnable {

    BlockingQueue<Integer> obj;

    public producer(BlockingQueue<Integer> obj)
    {
        this.obj = obj;
    }

    @Override public void run()
    {
        for (int i = 1; i <= 4; i++) {
            try {
                obj.put(i);
                System.out.println("Produced " + i);
            }
            catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}

class consumer implements Runnable {

    BlockingQueue<Integer> obj;

    int taken = -1;

    public consumer(BlockingQueue<Integer> obj)
    {
        this.obj = obj;
    }

    @Override public void run()
    {
        while (taken != 4) {
            try {
                taken = obj.take();
                System.out.println("Consumed " + taken);
            }
            catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}
```

**Output**

```
Produced 1
Produced 2
Produced 3
Produced 4
Consumed 1
Consumed 2
Consumed 3
Consumed 4
```

**注:**

*   上述程序可能会在每次运行时给出不同的生产和消费订单。但值得注意的是，所有产生的数字都会被消费掉，不会有任何线程间的通信问题。
*   **毒元素:**这个元素标志着生产-消费活动的结束，在上面的例子中，4 是毒元素。
*   如果事先不知道元素的数量，可以使用 [<u>链接锁定队列</u>](https://www.geeksforgeeks.org/linkedblockingqueue-class-in-java/) 。