# Java 中的可运行界面

> 原文:[https://www.geeksforgeeks.org/runnable-interface-in-java/](https://www.geeksforgeeks.org/runnable-interface-in-java/)

`java.lang.Runnable`是要由类实现的接口，该类的实例打算由线程执行。有两种方法可以开始一个新的线程——子类`Thread`和实现`Runnable`。当一个任务只需要覆盖`Runnable`的`run()`方法就可以完成时，不需要再子类化`Thread`。

**使用`Runnable`创建新`Thread`的步骤:**
**1。**创建`Runnable`实施者，实施`run()`方法。
**2。**实例化`Thread`类，并将实现者传递给`Thread`，`Thread`有一个接受`Runnable`实例的构造函数。
**3。**调用`Thread`实例的`start()`，开始内部调用实现者的`run()`。调用`start()`，创建一个新的`Thread`，执行`run()`中编写的代码。
直接调用`run()`并不会创建和启动一个新的`Thread`，它会在同一个线程中运行。要开始新的执行行，在线程上调用`start()`。
**例，**

```java
public class RunnableDemo {

    public static void main(String[] args)
    {
        System.out.println("Main thread is- "
                        + Thread.currentThread().getName());
        Thread t1 = new Thread(new RunnableDemo().new RunnableImpl());
        t1.start();
    }

    private class RunnableImpl implements Runnable {

        public void run()
        {
            System.out.println(Thread.currentThread().getName()
                             + ", executing run() method!");
        }
    }
}
```

输出:

```java
Main thread is- main
Thread-0, executing run() method!

```

输出显示程序中的两个活动线程——主线程和线程 0，主方法由主线程执行，但在`RunnableImpl`上调用 start 会创建并启动一个新线程——线程 0。

**当 Runnable 遇到异常时会发生什么？**
`Runnable`不能抛出勾选的异常但是`RuntimeException`可以从`run()`抛出。未捕获的异常由线程的异常处理程序处理，如果 JVM 不能处理或捕获异常，它将打印堆栈跟踪并终止流。
**例，**

```java
import java.io.FileNotFoundException;

public class RunnableDemo {

    public static void main(String[] args)
    {
        System.out.println("Main thread is- " +
                          Thread.currentThread().getName());
        Thread t1 = new Thread(new RunnableDemo().new RunnableImpl());
        t1.start();
    }

    private class RunnableImpl implements Runnable {

        public void run()
        {
            System.out.println(Thread.currentThread().getName()
                             + ", executing run() method!");
            /**
             * Checked exception can't be thrown, Runnable must
             * handle checked exception itself.
             */
            try {
                throw new FileNotFoundException();
            }
            catch (FileNotFoundException e) {
                System.out.println("Must catch here!");
                e.printStackTrace();
            }

            int r = 1 / 0;
            /*
             * Below commented line is an example
             * of thrown RuntimeException.
             */
            // throw new NullPointerException();
        }
    }
}
```

输出:

```java
java.io.FileNotFoundException
    at RunnableDemo$RunnableImpl.run(RunnableDemo.java:25)
    at java.lang.Thread.run(Thread.java:745)
Exception in thread "Thread-0" java.lang.ArithmeticException: / by zero
    at RunnableDemo$RunnableImpl.run(RunnableDemo.java:31)
    at java.lang.Thread.run(Thread.java:745)

```

输出显示`Runnable`不能抛出检查异常，`FileNotFoundException`在这种情况下，对于调用者，它必须在`run()`中处理检查异常，但是 RuntimeExceptions(抛出或自动生成)由 JVM 自动处理。

**参考文献:**
[http://www . javarag . com/2016/11/javalangrunnable-interface . html](http://www.javargon.com/2016/11/javalangrunnable-interface.html)