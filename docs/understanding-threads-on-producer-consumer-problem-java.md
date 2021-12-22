# 了解生产者消费者问题的线程| Java

> 原文:[https://www . geesforgeks . org/understanding-threads-on-producer-consumer-problem-Java/](https://www.geeksforgeeks.org/understanding-threads-on-producer-consumer-problem-java/)

线程是执行的一部分，即它是程序中独立的执行路径。一个程序可以有多个线程，这就产生了[多线程](https://www.geeksforgeeks.org/multithreading-in-java/)的概念。我们必须使用 [java.lang.Thread](https://www.geeksforgeeks.org/java-lang-thread-class-java/) 类才能使用一个线程来执行特定的任务。在本文中，让我们通过一个程序来看看线程的实现。
每当一个程序被执行时，JVM 首先检查“Main”方法的存在。如果方法存在，默认情况下它会创建一个线程，这个线程被称为“主线程”，因为它负责执行主方法中存在的语句。一个线程可以处于多种状态，本文对此进行了讨论。
创建线程有两种方式。它们是:

1.  通过为线程类创建一个对象。
2.  通过使用可运行接口。

**通过扩展 Thread 类来创建线程:**我们创建了一个扩展 java.lang.Thread 类的类。此类覆盖线程类中可用的 **run()** 方法。一根线在**运行()**方法中开始它的生命。我们创建一个线程类的对象，调用 **start()** 方法开始执行一个线程。 **Start()** 调用线程对象上的 **run()** 方法。让我们来看一个使用线程寻找阶乘的例子:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to find the factorial
// of a number by the implementation
// of threads using thread class

class ThreadImplement extends Thread {
    static int fact = 1;

    // Overriding the run method
    // to find the factorial of
    // a number 5
    public void run()
    {

        // Loop to compute the factorial
        for (int i = 1; i <= 5; i++)
            fact = fact * i;
        System.out.println(fact);
    }
}

// Class to create a thread and
// compute the factorial
public class GFG {
    public static void main(String[] args)
    {
        // Creating an object of the
        // thread class
        Thread t1
            = new Thread(new ThreadImplement());

        // Computing the above class
        t1.start();
    }
}
```

**Output:** 

```java
120
```

**通过实现可运行接口创建线程:**线程类实现[可运行接口](https://www.geeksforgeeks.org/runnable-interface-in-java/)，可运行接口只包含 **run()** 方法。线程类中有近 37 种方法，但我们通常使用 22 种。所有需要由线程执行的任务都必须放在 run()方法中，也就是说，我们必须重写 run()方法。为了开始一个线程，我们必须使用 **start()** 方法。启动线程后，该线程将执行 **run()** 方法中存在的语句。让我们使用可运行的接口
实现相同的阶乘程序

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to find the factorial
// of a number by the implementation
// of threads using runnable interface

class ThreadImplement implements Runnable {
    static int fact = 1;

    // Overriding the run method
    // to find the factorial of
    // a number 5
    public void run()
    {
        // Loop to compute the factorial
        for (int i = 1; i <= 5; i++)
            fact = fact * i;
        System.out.println(fact);
    }
}

// Class to create a thread and
// compute the factorial
public class GFG {
    public static void main(String[] args)
    {

        // Creating an object of the
        // thread class
        Thread t1
            = new Thread(new ThreadImplement());

        // Computing the above class
        t1.start();
    }
}
```

**Output:** 

```java
120
```

**Java 中的多线程:**在计算中，生产者-消费者问题(也称为有界缓冲区问题)是多进程同步问题的经典例子。这个问题描述了两个进程，生产者和消费者，它们共享一个公共的、固定大小的缓冲区作为队列。

*   生产者的工作是生成数据，将其放入缓冲区，然后重新开始。
*   与此同时，消费者正在消耗数据(即从缓冲区中删除数据)，一次一个。

在这个问题中，我们需要两个线程，线程 t1(产生数据)和线程 t2(消耗数据)。然而，这两个线程不应该同时运行。

下面是生产者-消费者问题的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to implement the
// producer consumer's problem

import java.lang.Thread;

// Producer class which extends the
// thread
class Producer extends Thread {

    // Creating a string buffer
    StringBuffer buffer;
    boolean dp = false;

    // Initializing the string buffer
    Producer()
    {
        buffer = new StringBuffer(4);
    }

    // Overriding the run method
    public void run()
    {
        synchronized (buffer)
        {

            // Adding the data into the
            // buffer
            for (int i = 0; i < 4; i++) {
                try {
                    buffer.append(i);
                    System.out.println("Produced " + i);
                }
                catch (Exception e) {
                    e.printStackTrace();
                }
            }

            // Notifying the buffer
            System.out.println("Buffer is FUll");
            buffer.notify();
        }
    }
}

// Consumer class which extends
// the thread
class Consumer extends Thread {

    // Creating the object of the
    // producer class
    Producer p;

    // Assigning the object of the
    // producer class
    Consumer(Producer temp)
    {
        p = temp;
    }

    // Overriding the run method
    public void run()
    {

        // Controlling the access of the
        // buffer to the shared producer
        synchronized (p.buffer)
        {
            try {
                p.buffer.wait();
            }
            catch (Exception e) {
                e.printStackTrace();
            }

            // Printing the values of the string buffer
            // and consuming the buffer
            for (int i = 0; i < 4; i++) {
                System.out.print(p.buffer.charAt(i) + " ");
            }
            System.out.println("\nBuffer is Empty");
        }
    }
}

// Main class to implement the
// Producer Consumer problem
class GFG {
    public static void main(String args[])
    {
        // Initially, there needs to be some data
        // in order to consume the data. So,
        // Producer object is created first
        Producer p = new Producer();

        // Sending this producer object
        // into the consumer
        Consumer c = new Consumer(p);
        Thread t1 = new Thread(p);
        Thread t2 = new Thread(c);

        // Since from the producer object,
        // we have already produced the data.
        // So, we start by consuming it.
        t2.start();
        t1.start();
    }
}
```

**Output:** 

```java
Produced 0
Produced 1
Produced 2
Produced 3
Buffer is FUll
0 1 2 3 
Buffer is Empty
```

**生产者消费者没有同步的问题:**上面的代码效率不高，因为 CPU 资源没有得到有效利用。线程正在等待处于等待状态的缓冲区。相反，我们可以通过终止这些线程并重新创建它们来有效地利用它们。也就是:

*   我们创建一个线程来产生数据。
*   一旦缓冲区满了，我们将终止该线程。
*   创建另一个线程来使用数据(此时生产者线程是死的)。
*   一旦缓冲区为空，消费者线程终止，生产者线程被创建并产生数据(此时消费者线程是死的)。

以下是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to implement the
// producer consumer's problem
// without using synchronization

import java.lang.Thread;

// Producer class which extends the
// thread
class Producer extends Thread {

    // Creating a string buffer
    StringBuffer buffer;

    // Initializing the string buffer
    Producer()
    {
        buffer = new StringBuffer(4);
    }

    // Overriding the run method
    public void run()
    {

        // Loop to add data into the
        // buffer
        for (int i = 0; i < 4; i++) {
            try {
                buffer.append(i);
                System.out.println("Produced " + i);
            }
            catch (Exception e) {

                // Exception is returned when
                // the buffer is not accessible
                e.printStackTrace();
            }
        }
        System.out.println("Buffer is FUll");

        // Creating a consumer object after
        // execution of the above method.
        // Here, this keyword refers to
        // the current object of the
        // producer. This object is passed
        // into the consumer to access the
        // created buffer
        Consumer c = new Consumer(this);
    }
}

// Consumer class which extends
// the thread
class Consumer extends Thread {
    Producer p;
    Thread t2;

    // Constructor to get the
    // producer object
    Consumer(Producer temp)
    {
        p = temp;

        // Creating a new thread for
        // the object
        t2 = new Thread(this);
        t2.start();
    }

    // Overriding the run method
    public void run()
    {
        try {

            // Printing the string buffer and
            // consuming it
            for (int i = 0; i < 4; i++) {
                System.out.print(p.buffer.charAt(i) + " ");
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
        System.out.println("\nBuffer is Empty");
    }
}

// Main class to implement the
// Producer Consumer problem
class Efficiency {
    public static void main(String args[])
    {
        // Producer object is created and
        // passed into the thread.
        Producer p = new Producer();
        Thread t1 = new Thread(p);

        // Here, instead of the same
        // thread waiting, a new thread
        // is created in the constructor
        // of the consumer class
        t1.start();
    }
}
```

**Output:** 

```java
Produced 0
Produced 1
Produced 2
Produced 3
Buffer is FUll
0 1 2 3 
Buffer is Empty
```

**修改生产者消费者的问题:**上述方法可以进一步改进，因为生产者和消费者正在使用相同的缓冲区。因此，不要使用多个线程，而是使用一个线程，这样最初缓冲区是空的，并且创建的线程充当生产者。一旦缓冲区满了，这个线程就充当一个使用者，消耗数据。然而，我们需要避免僵局。

以下是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to implement the
// producer consumer's problem
// using single thread
import java.lang.Thread;

// Producer class which extends the
// thread
class Producer extends Thread {

    // Creating a string buffer
    StringBuffer buffer;

    // Variable to avoid the deadlock
    boolean dp = false;
    Thread t1;
    Producer()
    {
        // Initializing the buffer
        buffer = new StringBuffer(4);

        // Creating a new thread with
        // the current object
        t1 = new Thread(this);
        t1.start();
    }

    // Overriding the run method
    public void run()
    {

        // Loop to produce the
        // data and add it to
        // the buffer
        for (int i = 0; i < 4; i++) {
            try {
                buffer.append(i);
                System.out.println("Produced " + i);
            }
            catch (Exception e) {
                e.printStackTrace();
            }
        }
        System.out.println("Buffer is FUll");

        // Creating a consumer object
        // by passing the current
        // producer object
        Consumer c = new Consumer(this);

        // Reinitializing the thread
        // with the new value of the
        // consumer object
        t1 = new Thread(c);
        t1.start();
    }
}

// Consumer class which extends
// the thread
class Consumer extends Thread {
    Producer p;

    // Constructor to initialize
    // with the producer object
    Consumer(Producer temp)
    {
        p = temp;
    }

    // Overriding the run method
    public void run()
    {
        try {

            // Loop to print the buffer and
            // consume the values
            for (int i = 0; i < 4; i++) {
                System.out.print(p.buffer.charAt(i) + " ");
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
        System.out.println("\nBuffer is Empty");
    }
}

// Main class to implement the
// Producer Consumer problem
class GFG {
    public static void main(String args[])
    {

        // Creating the object of the
        // producer
        Producer p = new Producer();
    }
}
```

**Output:** 

```java
Produced 0
Produced 1
Produced 2
Produced 3
Buffer is FUll
0 1 2 3 
Buffer is Empty
```