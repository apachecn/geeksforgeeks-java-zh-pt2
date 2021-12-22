# 用 Java 调度线程池执行器类

> 原文:[https://www . geeksforgeeks . org/scheduledthreadpoolexecutor-class-in-Java/](https://www.geeksforgeeks.org/scheduledthreadpoolexecutor-class-in-java/)

Java 中的 ScheduledThreadPoolExecutor 类是 java.util.concurrent package 中定义的 ThreadPoolExecutor 类的子类。从它的名字可以清楚地看出，当我们想要安排任务重复运行或在给定延迟后运行一段时间时，这个类是有用的。它创建了一个固定大小的线程池。所以当它启动时，需要给它 corePoolSize(线程池[中的线程数](https://www.geeksforgeeks.org/thread-pools-java/))。

**等级等级:**

![ScheduledThreadPoolExecutor-Class-in-Java](img/03fb73a7e5d0db40efcf9066c6fd2b1a.png)

**施工人员:**

*   **ScheduledThreadPoolExecutor(int corePoolSize)**:用给定的池大小创建一个新的 ScheduledThreadPoolExecutor 对象。需要注意的是，它创建了一个固定大小的线程池，因此一旦给定了 corePoolSize，就不能增加线程池的大小。
*   **ScheduledThreadPoolExecutor(int corePoolSize，ThreadFactory threadFactory)** :用给定的参数创建一个新的 ScheduledThreadPoolExecutor 对象。第一个参数是线程池的大小，第二个参数是 ThreadFactory 对象，在 ScheduledThreadPoolExecutor 创建新线程时使用。
*   **ScheduledThreadPoolExecutor(int corePoolSize，RejectedExecutionHandler)处理程序)**:使用给定的 corePoolSize(threadpoolexecutor)创建一个新的 ScheduledThreadPoolExecutor 对象，以及在任务执行被拒绝时(当工作队列已满或执行被阻止时)使用的处理程序。
*   **ScheduledThreadPoolExecutor(int corePoolSize，ThreadFactory threadFactory，RejectedExecutionHandler 处理程序)**:用给定的参数创建一个新的 ScheduledThreadPoolExecutor 对象。

除了这些构造函数之外，还有另一种获取 ScheduledThreadPoolExecutor 对象的方法。我们可以使用**Executors . newscheduledthreadpool(int corePoolSize)**Executors 类定义的工厂方法。它返回一个 ScheduledExecutorService 对象，该对象可以类型转换为 ScheduledThreadPoolExecutor 对象。

> `ScheduledThreadPoolExecutor threadPool = (ScheduledThreadPoolExecutor)Executors.newScheduledThreadPool(4);`

**例 1** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrates ScheduleThreadPoolExecutor
// class
import java.util.*;
import java.util.concurrent.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        // Creating a ScheduledThreadPoolExecutor object
        ScheduledThreadPoolExecutor threadPool
            = new ScheduledThreadPoolExecutor(2);

        // Creating two Runnable objects
        Runnable task1 = new Command("task1");
        Runnable task2 = new Command("task2");

        // Printing the current time in seconds
        System.out.println(
            "Current time : "
            + Calendar.getInstance().get(Calendar.SECOND));

        // Scheduling the first task which will execute
        // after 2 seconds
        threadPool.schedule(task1, 2, TimeUnit.SECONDS);

        // Scheduling the second task which will execute
        // after 5 seconds
        threadPool.schedule(task2, 5, TimeUnit.SECONDS);

        // Remember to shut sown the Thread Pool
        threadPool.shutdown();
    }
}

// Class that implements the Runnable interface
class Command implements Runnable {
    String taskName;
    public Command(String taskName)
    {
        this.taskName = taskName;
    }
    public void run()
    {
        System.out.println(
            "Task name : " + this.taskName + " Current time: "
            + Calendar.getInstance().get(Calendar.SECOND));
    }
}
```

**输出**:

```
Current time : 51
Task name : task1 Current time : 53
Task name : task2 Current time : 56

```

这里，第一个任务在两秒钟延迟后执行，第二个任务在五秒钟后执行。

**例**T2【2】T3:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrates ScheduleThreadPoolExecutor
// class
import java.util.*;
import java.util.concurrent.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        // Creating a ScheduledThreadPoolExecutor object
        ScheduledThreadPoolExecutor threadPool
            = new ScheduledThreadPoolExecutor(2);

        // Creating two Runnable objects
        Runnable task1 = new Command("task1");
        Runnable task2 = new Command("task2");

        // Printing the current time in seconds
        System.out.println(
            "Current time:"
            + Calendar.getInstance().get(Calendar.SECOND));

        // Scheduling the first task which will execute
        // after 2 seconds and then repeats periodically with
        // a period of 8 seconds
        threadPool.scheduleAtFixedRate(task1, 2, 8,
                                       TimeUnit.SECONDS);

        // Scheduling the second task which will execute
        // after 5 seconds and then there will be a delay of
        // 5 seconds between the completion
        // of one execution and the commencement of the next
        // execution
        threadPool.scheduleWithFixedDelay(task2, 5, 5,
                                          TimeUnit.SECONDS);

        // Wait for 30 seconds
        try {
            Thread.sleep(30000);
        }
        catch (Exception e) {
            e.printStackTrace();
        }

        // Remember to shut sown the Thread Pool
        threadPool.shutdown();
    }
}

// Class that implements Runnable interface
class Command implements Runnable {
    String taskName;
    public Command(String taskName)
    {
        this.taskName = taskName;
    }
    public void run()
    {
        try {
            System.out.println("Task name : "
                               + this.taskName
                               + " Current time : "
                               + Calendar.getInstance().get(
                                     Calendar.SECOND));
            Thread.sleep(2000);
            System.out.println("Executed : " + this.taskName
                               + " Current time : "
                               + Calendar.getInstance().get(
                                     Calendar.SECOND));
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**输出**:

```
Current time:26
Task name : task1 Current time : 28
Executed : task1 Current time : 30
Task name : task2 Current time : 31
Executed : task2 Current time : 33
Task name : task1 Current time : 36
Executed : task1 Current time : 38
Task name : task2 Current time : 38
Executed : task2 Current time : 40
Task name : task1 Current time : 44
Task name : task2 Current time : 45
Executed : task1 Current time : 46
Executed : task2 Current time : 47
Task name : task1 Current time : 52
Task name : task2 Current time : 52
Executed : task1 Current time : 54
Executed : task2 Current time : 54

```

这里，第一个任务将在两秒钟后执行，然后在八秒钟后定期重复。第二个任务将在五秒钟后执行，然后在一次执行完成和下一次执行开始之间会有五秒钟的延迟。

### 方法

<figure class="table">

| 

**方法**

 | 

**描述**

 |
| --- | --- |
| 装饰任务(可调用<v>可调用，运行可调度未来<v>任务)</v></v> | 修改或替换用于执行可调用。 |
| 装饰任务(可运行可运行，可运行调度未来<v>任务)</v> | 修改或替换用于执行可运行的任务。 |
| 执行(可运行命令) | 以零要求延迟执行命令。 |
| getcontinueeexistingperiodicastsksaftershutdowpolicy() | 获取关于是否继续执行现有定期任务的策略，即使此执行器已关闭。 |
| getexecutexistingdelayedtaskssaftershutdowpolicy() | 获取关于是否执行现有延迟任务的策略，即使该执行器已关闭。 |
| getQueue() | 返回此执行器使用的任务队列。 |
| getRemoveOnCancelPolicy() | 获取取消任务时是否应立即从工作队列中删除的策略。 |
| 计划(可调用<v>可调用，长延迟，时间单位单位)</v> | 创建并执行一个在给定延迟后启用的调度未来。 |
| 计划(可运行命令、长延迟、时间单位单位) | 创建并执行一个一次性动作，该动作在给定延迟后被启用。 |
| 调度固定日期(可运行命令，长初始时间，长周期，时间单位单位) | 创建并执行一个周期性动作，该动作在给定延迟后首先被启用，随后在给定周期内被启用。 |
| scheduleWithFixedDelay(可运行命令，长初始延迟，长延迟，时间单位单位) | 创建并执行一个周期性动作，该动作在给定延迟后启用，随后在一个执行的终止和下一个执行的开始之间具有给定的延迟。 |
| setcontinexietworkperiodic safterhutdownpolicy(布尔值) | 设置是否继续执行现有定期任务的策略，即使此执行器已关闭。 |
| setexecutexistingdelayedtaskssaftershutdowpolicy(布尔值) | 设置是否执行现有延迟任务的策略，即使此执行器已关闭。 |
| setRemoveOnCancelPolicy() | 设置取消任务时是否应立即将其从工作队列中删除的策略。 |
| 关机() | 启动有序关机，在此过程中，将执行以前提交的任务，但不会接受任何新任务。 |
| shutdownNow() | 尝试停止所有正在执行的任务会暂停等待任务的处理，并返回等待执行的任务列表。 |
| 提交(可调用<t>任务)</t> | 提交一个返回值任务以供执行，并返回一个代表任务待定结果的未来值。 |
| 提交(可运行任务) | 提交可运行的任务以供执行，并返回代表该任务的未来。 |
| 提交(可运行任务，测试结果) | 提交可运行的任务以供执行，并返回代表该任务的未来。 |

</figure>