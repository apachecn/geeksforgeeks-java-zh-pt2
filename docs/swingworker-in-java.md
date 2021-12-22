# Java 中的 swing worker

> 原文:[https://www.geeksforgeeks.org/swingworker-in-java/](https://www.geeksforgeeks.org/swingworker-in-java/)

SwingWorker 是为 Java 编程语言的 Swing 库开发的抽象类。它用于在后台线程中执行冗长的图形用户界面交互任务。在开发应用程序时，当图形用户界面试图完成一些巨大或冗长的任务时，它有时会挂起。这种滞后是一个很大的瓶颈。为此，开发了 swingworker，它在 GUI 仍然保持响应的情况下，在不同的线程上调度这个冗长任务的执行。

Java 语言有**三个线程**，即:

*   **当前线程**(初始线程):这是执行初始应用逻辑的线程。
*   **事件调度线程**:所有事件处理代码都在这个线程上执行。
*   **工作线程**:也称为后台线程，执行所有耗时的后台任务。

SwingWorker 允许用户在 Worker 线程上调度后台任务的执行。但是，用户如何知道任务何时完成执行，或者用户是否需要根据线程执行更新图形用户界面(在初始线程上运行)？这意味着我们也需要[线程间通信](htctp://www.geeksforgeeks.org/inter-thread-communication-java/)。SwingWorker 是为这种棘手的情况设计的，它在事件调度线程上提供通信。

**swing worker 的重要方法:**

1.  **doInBackground()** :这个函数包含了我们后台任务的逻辑，也就是我们希望线程做什么。该函数在工作线程上运行，并且是实现所必需的。

    ```
    protected abstract T doInBackground()
                                 throws Exception
    Computes a result, or throws an exception if unable to do so. 
    This method is executed in a background thread.
    Returns:
    the computed result
    Throws:
    Exception - if unable to compute a result
    ```

2.  **done()** :这个函数在线程执行完的时候被调用。此外，doInBackground()函数返回的任何值都可以使用 get()在该函数中接收。此外，可以在此功能中对图形用户界面进行更新。因此，在 doInBackground 方法完成后，函数在事件调度线程上执行。

    ```
    protected void done()
    ```

3.  **execute()** :调度这个 SwingWorker 在工作线程上执行。

    ```
    public final void execute()
    ```

4.  **publish()** :该方法将从 doInBackground 方法内部使用，以传递中间结果，供流程方法内部的事件调度线程处理。

    ```
    protected final void publish(V... chunks)
    ```

5.  **进程()**:在事件调度线程上异步接收来自发布方法的数据块。因为这个方法是异步调用的，所以 publish()可能被调用了多次。

    ```
    protected void process(List chunks)
    Parameters:
    chunks - intermediate results to process
    ```

6.  **run():** 将此未来设置为计算结果，除非它已被取消。

    ```
    public final void run()
    ```

7.  **设置进度:**设置进度绑定属性。该值应该在 0 到 100 之间。

    ```
    protected final void setProgress(int progress)

    Example:
    setProgress(1);
    setProgress(2);
    setProgress(3);

    might result in a single PropertyChangeListener 
    notification with the value 3.
    Parameters:
    progress - the progress value to set
    Throws:
    IllegalArgumentException - is value not from 0 to 100
    ```

8.  **获取进度:**返回进度绑定属性。

    ```
    public final int getProgress()
    Returns:
    the progress bound property.
    ```

9.  **取消:**尝试取消此任务的执行。如果任务已经完成、已经取消或由于其他原因无法取消，此尝试将失败。如果成功，并且在调用取消时此任务尚未开始，则此任务不应运行。如果任务已经开始，则 may 中断运行参数确定执行此任务的线程是否应该中断以尝试停止任务。
    此方法返回后，后续对 Future.isDone()的调用将始终返回 true。如果此方法返回 true，对 Future.isCancelled()的后续调用将始终返回 true。

    ```
    public final boolean cancel(boolean mayInterruptIfRunning)
    Parameters:
    mayInterruptIfRunning - true if the thread executing this task 
    should be interrupted; otherwise, in-progress tasks 
    are allowed to complete
    Returns:
    false if the task could not be cancelled, typically 
    because it has already completed normally; true otherwise
    ```

10.  **取消:**如果该任务在正常完成前被取消，则返回真。

    ```
    public final boolean isCancelled()
    Returns:
    true if this task was cancelled before it completed
    ```

11.  **isDone:** 如果任务完成，返回 true。完成可能是由于正常终止、异常或取消，在所有这些情况下，该方法将返回 true。

    ```
    public final boolean isDone()
    Returns:
    true if this task completed
    ```

12.  **获取:**等待计算完成，然后检索其结果。

    ```
    public final T get()
                throws InterruptedException,
                       ExecutionException
    ```

13.  **getState:** 返回 SwingWorker 状态绑定属性。

    ```
    public final SwingWorker.StateValue getState()
    Returns:
    the current state

    ```

**举例说明 SwingWorker**

我们希望或线程在按钮被点击时开始执行。请参见按钮的操作侦听器中的 startThread()。startThread 函数定义了一个新的 swingworker 类型 **javax.swing.SwingWorker** ，其中，
T–这个 SwingWorker 的 doInBackground 和 get 方法返回的结果类型，在下面的代码中是 String。
V–该 SwingWorker 的发布和处理方法用于执行中间结果的类型，在下面的代码中为 Integer。

```
// Java program to illustrate 
// working of SwingWorker
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.WindowAdapter;
import java.awt.event.WindowEvent;
import java.util.List;
import java.util.concurrent.ExecutionException;

import javax.swing.*;

public class SwingWorkerSample 
{

    private static JLabel statusLabel;
    private static JFrame mainFrame;

    public static void swingWorkerSample () 
    {
        mainFrame = new JFrame("Swing Worker");
        mainFrame.setSize(400, 400);
        mainFrame.setLayout(new GridLayout(2,1));

        mainFrame.addWindowListener(new WindowAdapter() 
        {

            @Override
            public void windowClosing(WindowEvent e) 
            {
                System.exit(0);
            }

        });

        statusLabel = new JLabel("Not Completed", JLabel.CENTER);
        mainFrame.add(statusLabel);

        JButton btn = new JButton("Start counter");
        btn.setPreferredSize(new Dimension(5,5));

        btn.addActionListener(new ActionListener() 
        {

            @Override
            public void actionPerformed(ActionEvent e) 
            {
                System.out.println("Button clicked, thread started");
                startThread(); 
            }

        });

        mainFrame.add(btn);
        mainFrame.setVisible(true);
    }

    private static void startThread() 
    {

        SwingWorker sw1 = new SwingWorker() 
        {

            @Override
            protected String doInBackground() throws Exception 
            {
                // define what thread will do here
                for ( int i=10; i>=0; i-- ) 
                {
                    Thread.sleep(100);
                    System.out.println("Value in thread : " + i);
                    publish(i);
                }

                String res = "Finished Execution";
                return res;
            }

            @Override
            protected void process(List chunks)
            {
                // define what the event dispatch thread 
                // will do with the intermediate results received
                // while the thread is executing
                int val = chunks.get(chunks.size()-1);

                statusLabel.setText(String.valueOf(val));
            }

            @Override
            protected void done() 
            {
                // this method is called when the background 
                // thread finishes execution
                try 
                {
                    String statusMsg = get();
                    System.out.println("Inside done function");
                    statusLabel.setText(statusMsg);

                } 
                catch (InterruptedException e) 
                {
                    e.printStackTrace();
                } 
                catch (ExecutionException e) 
                {
                    e.printStackTrace();
                }
            }
        };

        // executes the swingworker on worker thread
        sw1.execute(); 
    }

    public static void main(String[] args) 
    {
        swingWorkerSample();

    }

}
```

1.  运行上面的代码，点击按钮，你会看到一个计数器递减。同时使用用户界面做任何事情，它仍然会有响应。
2.  List chunks 是 process()函数的参数，包含线程发布的每个结果的列表，直到此时数据类型为 Integer。数据类型整数应该与我们的 swingworker 声明相匹配。

**应用程序:**
创建显示任务进度的进度条。

**参考文献:**
[链接 1](https://docs.oracle.com/javase/7/docs/api/javax/swing/SwingWorker.html)
链接 2

本文由 **Ekta Goel** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。