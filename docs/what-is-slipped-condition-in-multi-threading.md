# 什么是多线程中的打滑情况？

> 原文:[https://www . geesforgeks . org/什么是多线程中的滑动条件/](https://www.geeksforgeeks.org/what-is-slipped-condition-in-multi-threading/)

**滑移条件**是一种特殊类型的[竞争条件](https://www.geeksforgeeks.org/operating-system-process-synchronization/)，它可能发生在多线程应用程序中。在这种情况下，在执行与其相关的活动之前，在读取条件和**之后**暂停线程。它很少发生，但是，如果结果不如预期，人们必须寻找它。****

**例**:假设有两根**线 A 和线 B** 想要加工一根**线 S** 。首先，启动**线程 A** ，检查是否还有字符需要处理，最初整个字符串都可以处理，所以条件为真。现在**螺纹 A** 暂停，**螺纹 B** 开始。它再次检查条件，评估为真，然后处理整个字符串 S。现在，当**线程 A** 再次开始执行时，**字符串 S** 此时已被完全处理，因此出现错误。这就是所谓的滑倒。

**在爪哇演示打滑情况的程序**

```
// Java program to demonstrate
// slipped conditions

public class Main {
    public static void main(String[] args)
    {
        ReadingThread readingThread
            = new ReadingThread();
        SlippedThread slippedThread
            = new SlippedThread();

        slippedThread.start();
        readingThread.start();
    }
}

class CommonResource {
    static final String string = "Hello";
    static int pointerPosition = 0;
}

// Thread to demonstrate a slipped condition
class SlippedThread extends Thread {
    @Override
    public void run()
    {
        // Check if any characters
        // are left to process
        if (CommonResource.pointerPosition
            != CommonResource.string.length()) {
            System.out.println("Characters left! "
                               + "I can process the string");

            // Cause the thread to wait to cause
            // a slipped condition
            try {
                synchronized (this)
                {
                    wait(500);
                }
            }

            catch (InterruptedException e) {
                System.out.println(e);
            }

            try {
                while (CommonResource.pointerPosition
                       < CommonResource.string.length()) {

                    System.out.println("Thread1 "
                                       + CommonResource.string
                                             .charAt(
                                                 CommonResource
                                                     .pointerPosition));
                    CommonResource.pointerPosition++;
                }
            }

            catch (StringIndexOutOfBoundsException e) {
                System.out.println("\nNo more character left"
                                   + " to process. This is a"
                                   + " slipped condition");
            }
        }
    }
}

// Thread to process the whole String
class ReadingThread extends Thread {
    @Override
    public void run()
    {
        System.out.println("Thread2 trying to "
                           + "process the string");
        while (CommonResource.pointerPosition
               < CommonResource.string.length()) {

            System.out.print("Thread2 "
                             + CommonResource.string
                                   .charAt(
                                       CommonResource
                                           .pointerPosition));
            CommonResource.pointerPosition++;
        }
    }
}
```

**输出:**

```
Characters left! I can process the string
Thread2 trying to process the string
Thread2 H
Thread2 e
Thread2 l
Thread2 l
Thread2 o
No more character left to process. This is a slipped condition

```