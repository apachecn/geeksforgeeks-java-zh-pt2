# 什么是 Java 执行器框架？

> 原文:[https://www . geesforgeks . org/what-is-Java-executor-framework/](https://www.geeksforgeeks.org/what-is-java-executor-framework/)

随着当今处理器中可用内核数量的增加，以及实现更大吞吐量的需求不断增加，多线程应用编程接口变得越来越受欢迎。Java 提供了自己的多线程框架，称为 Java 执行器框架。

与 JDK 5 一起发布的 Java executor 框架([Java . util . concurrent . executor](https://www.geeksforgeeks.org/java-util-concurrent-executor-interface-with-examples/))用于运行 Runnable 对象，而无需每次都创建新的线程，并且主要是重用已经创建的线程。我们都知道有两种方法可以在 java 中创建线程。如果你想了解更多关于它们的比较，请阅读[如何用 Java 创建线程。](https://www.geeksforgeeks.org/multithreading-in-java/)

Java . util . concurrent . executors 提供了用于创建工作线程的[线程池](https://www.geeksforgeeks.org/thread-pools-java/)的工厂方法。线程池通过保持线程活动和重用线程来克服这个问题。池中的线程可以处理的任何多余任务都保存在队列中。一旦任何线程获得空闲，它们就会从这个队列中获取下一个任务。对于 JDK 提供的开箱即用的执行者来说，这个任务队列基本上是无界的。

**下面列出了一些类型的 Java 执行器:**

1.  SingleThreadExecutor
2.  固定线程池（n）
3.  缓存读取池
4.  调度执行程序

让我们详细讨论一下这些流行的 java 执行器，在实现它们之前，它们会做些什么来获得更好的想法。

**执行者 1:** 单线程执行者

通过调用 Executors 类的静态[*newsingleetheadexecutor()*](https://www.geeksforgeeks.org/difference-between-executorservice-execute-and-submit-method-in-java/)方法可以获得一个单线程池。它用于按顺序执行任务。

**语法:**

```java
ExecutorService executor = Executors.newSingleThreadExecutor();
```

**执行器 2：** 固定线程池（n）

顾名思义，它是由固定数量的线程组成的线程池。提交给执行器的任务由 n 个线程执行，如果有更多的任务，则存储在 LinkedBlockingQueue 中。它使用阻塞队列。

**语法:**

```java
ExecutorService fixedPool = Executors.newFixedThreadPool(2);
```

**执行者 3:** 缓存线程池

创建一个线程池，该线程池根据需要创建新的线程，但是当以前构建的线程可用时，将重用它们。如果可用，对执行的调用将重用以前构造的线程。如果现有线程不可用，将创建一个新线程并将其添加到池中。它使用一个[同步队列](https://www.geeksforgeeks.org/java-program-to-implement-synchronousqueue-api/)队列。

```java
ExecutorService executorService = Executors.newCachedThreadPool();
```

**执行者 4:** 调度器

预定的执行器基于扩展了[执行器服务接口](https://www.geeksforgeeks.org/java-util-concurrent-executorservice-interface-with-examples/)的接口[调度执行器服务](https://www.geeksforgeeks.org/scheduledexecutorservice-interface-in-java/)。当我们有一个任务需要定期运行，或者我们希望延迟某个任务时，使用这个执行器。

```java
ScheduledExecutorService scheduledExecService = Executors.newScheduledThreadPool(1);
```

*   可以使用以下两种方法之一来安排任务:
    *   **调度固定日期**:以固定的时间间隔执行任务，不考虑前一个任务何时结束。
    *   **计划延迟**:只有在当前任务完成后，才会开始延迟倒计时

**语法:**

```java
scheduledExecService.scheduleAtFixedRate(Runnable command, long initialDelay, long period, TimeUnit unit)
```

```java
scheduledExecService.scheduleWithFixedDelay(Runnable command, long initialDelay, long period, TimeUnit unit)
```

> [未来物体](https://www.geeksforgeeks.org/future-and-futuretask-in-java/)
> 
> 提交给执行器执行的任务的结果可以使用执行器返回的未来对象来访问。未来可以被认为是执行者向打电话者做出的承诺。未来接口主要用于获取 Callable 结果的结果。每当任务执行完成时，它都由执行器在这个 Future 对象中设置。

**语法:**

```java
Future<String> result = executorService.submit(callableTask);
```

**实现:**创建并执行一个简单的执行器，在这个执行器中我们将创建一个任务，并在一个固定的池中执行它

*   任务类实现了可调用，并被参数化为字符串类型。它也被声明为抛出异常。
*   现在，为了在类“任务”中执行任务，我们必须实例化任务类，并将其传递给执行器执行。
*   打印并显示未来对象返回的结果

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program demonstrating Introduction to Java Executor
// Framework

// Importing concurrent classes from java.util package
import java.util.concurrent.*;

// Class 1
// Helper Class implementing runnable interface Callable
class Task implements Callable<String> {
    // Member variable of this class
    private String message;

    // Constructor of this class
    public Task(String message)
    {
        // This keyword refers to current instance itself
        this.message = message;
    }

    // Method of this Class
    public String call() throws Exception
    {
        return "Hiiii " + message + "!";
    }
}
// Class 2
// Main Class
// ExecutorExample
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of above class
        // in the main() method
        Task task = new Task("GeeksForGeeks");

        // Creating object of ExecutorService class and
        // Future object Class
        ExecutorService executorService
            = Executors.newFixedThreadPool(4);
        Future<String> result
            = executorService.submit(task);

        // Try block to check for exceptions
        try {
            System.out.println(result.get());
        }

        // Catch block to handle the exception
        catch (InterruptedException
               | ExecutionException e) {

            // Display message only
            System.out.println(
                "Error occured while executing the submitted task");

            // Print the line number where exception occured
            e.printStackTrace();
        }

        // Cleaning resource and shutting down JVM by
        // saving JVM state using shutdown() method
        executorService.shutdown();
    }
}
```

**输出:**

```java
Hiiii GeeksForGeeks
```

> **结论:**
> 
> 随着处理器时钟速度难以提高，多线程越来越成为主流。然而，由于所涉及的复杂性，处理每个线程的生命周期非常困难。