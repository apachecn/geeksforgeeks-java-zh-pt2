# 在 Java 中使用两个线程以递增的顺序打印偶数和奇数

> 原文:[https://www . geesforgeks . org/print-偶数和奇数-按递增顺序-使用 java 中的两个线程/](https://www.geeksforgeeks.org/print-even-and-odd-numbers-in-increasing-order-using-two-threads-in-java/)

**先决条件:** [多线程](https://www.geeksforgeeks.org/multithreading-c-2/)

给定一个整数 **N，**任务是编写 [Java 程序](https://www.geeksforgeeks.org/java/)使用两个[线程](https://www.geeksforgeeks.org/main-thread-java/)以递增的顺序打印第一个 **N 个**自然数。

**示例:**

> **输入:**N = 10
> T3】输出: 1 2 3 4 5 6 7 8 9 10
> 
> **输入:**N = 18
> T3】输出: 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18

**做法:**思路是创建两个线程，用一个线程打印偶数，用另一个线程打印奇数。以下是步骤:

*   使用以下语法创建两个线程 **T1** 和 **T2** ，其中 **T1** 和 **T2** 分别用于打印奇数和偶数。

    > Thread T1 = new Thread(new Runnable(){
    > public void run(){ mt . printevennumber()；}
    > })；
    > 
    > Thread T2 = new Thread(new Runnable(){
    > public void run(){ mt . print odd number()；}
    > })；
    > 
    > 其中，
    > **打印奇数()**打印所有奇数直到 **N** 、
    > T6【打印偶数()打印所有偶数直到 **N** 。

*   维护一个全局计数器变量，并使用下面的函数启动两个线程:

    > t1。start()；
    > T2。start()；

*   如果计数器在线程 **T1** 中为偶数，则等待线程 **T2** 打印该偶数。否则，打印该奇数，增加计数器并使用功能[通知()](https://www.geeksforgeeks.org/difference-notify-notifyall-java/)通知线程 **T2** 。
*   如果线程 **T2** 中的计数器为奇数，则等待线程 **T1** 打印该偶数。否则，打印偶数，增加计数器，并使用通知()功能通知线程 **T1** 。

以下是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program for the above approach

public class GFG {

    // Starting counter
    int counter = 1;

    static int N;

    // Function to print odd numbers
    public void printOddNumber()
    {
        synchronized (this)
        {
            // Print number till the N
            while (counter < N) {

                // If count is even then print
                while (counter % 2 == 0) {

                    // Exception handle
                    try {
                        wait();
                    }
                    catch (
                        InterruptedException e) {
                        e.printStackTrace();
                    }
                }

                // Print the number
                System.out.print(counter + " ");

                // Increment counter
                counter++;

                // Notify to second thread
                notify();
            }
        }
    }

    // Function to print even numbers
    public void printEvenNumber()
    {
        synchronized (this)
        {
            // Print number till the N
            while (counter < N) {

                // If count is odd then print
                while (counter % 2 == 1) {

                    // Exception handle
                    try {
                        wait();
                    }
                    catch (
                        InterruptedException e) {
                        e.printStackTrace();
                    }
                }

                // Print the number
                System.out.print(
                    counter + " ");

                // Increment counter
                counter++;

                // Notify to 2nd thread
                notify();
            }
        }
    }

    // Driver Code
    public static void main(String[] args)
    {
        // Given Number N
        N = 10;

        // Create an object of class
        GFG mt = new GFG();

        // Create thread t1
        Thread t1 = new Thread(new Runnable() {
            public void run()
            {
                mt.printEvenNumber();
            }
        });

        // Create thread t2
        Thread t2 = new Thread(new Runnable() {
            public void run()
            {
                mt.printOddNumber();
            }
        });

        // Start both threads
        t1.start();
        t2.start();
    }
}
```

**Output:**

```java
1 2 3 4 5 6 7 8 9 10

```

 ***时间复杂度:**O(N)
T5】辅助空间: O(1)*