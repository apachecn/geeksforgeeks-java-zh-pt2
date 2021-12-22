# 理解 Java 中的内存溢出异常

> 原文:[https://www . geesforgeks . org/understanding-out of memory error-exception-Java/](https://www.geeksforgeeks.org/understanding-outofmemoryerror-exception-java/)

在 Java 中，所有对象都存储在堆中。它们是使用[新的](https://www.geeksforgeeks.org/new-operator-vs-newinstance-method-java/)运算符分配的。Java 中的 OutOfMemoryError 异常如下所示:

```java
Exception in thread "main" java.lang.OutOfMemoryError: Java heap space

```

通常，当 Java 虚拟机因为内存不足而无法分配对象，并且垃圾收集器无法提供更多内存时，就会引发此错误。

**OutOfMemoryError** 通常意味着你做错了什么，要么是拿着对象太久，要么是试图一次处理太多数据。有时，它表示您无法控制的问题，例如缓存字符串的第三方库，或者部署后不清理的应用程序服务器。有时，它与堆上的对象无关。

当无法满足本机分配时(例如，如果交换空间不足)，本机库代码也会引发 **java.lang.OutOfMemoryError 异常**。让我们了解当内存不足错误可能发生时的各种情况。

**症状还是根本原因？**

为了找到原因，异常的文本在末尾包含了一条详细的消息。让我们检查所有的错误。

1.  **Error 1 – Java heap space :** This error arises due to the applications that make excessive use of finalizers. If a class has a finalize method, then objects of that type do not have their space reclaimed at [garbage collection](https://www.geeksforgeeks.org/garbage-collection-java/) time. Instead, after garbage collection, the objects are queued for finalization, which occurs at a later time. Implementation:
    *   终结器由服务于终结队列的守护线程执行。
    *   如果终结器线程跟不上终结队列，那么 Java 堆可能会填满，并且会引发这种类型的 OutOfMemoryError 异常。
    *   这个问题也可以像配置问题一样简单，指定的堆大小(或者默认大小，如果没有指定的话)对于应用程序来说是不够的。

    ```java
    // Java program to illustrate
    // Heap error
    import java.util.*;

    public class Heap {
        static List<String> list = new ArrayList<String>();

    public static void main(String args[]) throws Exception
        {
            Integer[] array = new Integer[10000 * 10000];
        }
    }
    ```

    当您执行上面的代码时，您可能希望它永远运行，没有任何问题。因此，随着时间的推移，随着不断使用泄漏的代码，“缓存”的结果最终会消耗大量的 Java 堆空间，当泄漏的内存填满堆区域中的所有可用内存并且垃圾收集无法清理它时，就会抛出**Java . lang . out of memory error:Java 堆空间**。

    **预防:**检查如何在[中监控待完成的对象。](https://docs.oracle.com/javase/8/docs/technotes/guides/troubleshoot/memleaks004.html#CIHCDBJB)

2.  **Error 2 – GC Overhead limit exceeded :** This error indicates that the [garbage collector](https://www.geeksforgeeks.org/garbage-collection-java/) is running all the time and Java program is making very slow progress. After a garbage collection, if the Java process is spending more than approximately 98% of its time doing garbage collection and if it is recovering less than 2% of the heap and has been doing so far the last 5 (compile time constant) consecutive garbage collections, then a **java.lang.OutOfMemoryError** is thrown.
    This exception is typically thrown because the **amount of live data barely fits into the Java heap** having little free space for new allocations.

    ```java
    // Java program to illustrate
    // GC Overhead limit exceeded
    import java.util.*;

    public class Wrapper {
    public static void main(String args[]) throws Exception
        {
            Map m = new HashMap();
            m = System.getProperties();
            Random r = new Random();
            while (true) {
                m.put(r.nextInt(), "randomValue");
            }
        }
    }
    ```

    如果您将使用**Java-xmx10m-XX:+UseParallelGC Wrapper**运行该程序，那么输出将如下所示:

    ```java
    Exception in thread "main" java.lang.OutOfMemoryError: GC overhead limit exceeded
        at java.lang.Integer.valueOf(Integer.java:832)
        at Wrapper.main(error.java:9)

    ```

    **预防:**增加堆大小，用命令行标志 **-XX:-UseGCOverheadLimit 关闭。**

3.  **Error 3 – Permgen space is thrown :** Java memory is separated into different regions. The size of all those regions, including the permgen area, is set during the JVM launch. If you do not set the sizes yourself, platform-specific defaults will be used.
    The **java.lang.OutOfMemoryError**: PermGen space error indicates that the Permanent Generation’s area in memory is exhausted.

    ```java
    // Java program to illustrate
    // Permgen Space error
    import javassist.ClassPool;

    public class Permgen {
        static ClassPool classPool = ClassPool.getDefault();

    public static void main(String args[]) throws Exception
        {
            for (int i = 0; i < 1000000000; i++) {
                Class c = classPool.makeClass(com.saket.demo.Permgen" + i).toClass();
                System.out.println(c.getName());
            }
        }
    }
    ```

    在上面的示例代码中，代码在循环中迭代，并在运行时生成类。类生成的复杂性由 [Javassist](http://jboss-javassist.github.io/javassist/) 库处理。
    运行上面的代码将继续生成新的类并且**将它们的定义加载到 Permgen 空间中，直到空间被完全利用**并且抛出 Java . lang . out of memory error:Permgen 空间。
    **预防:**当应用程序启动过程中出现 PermGen 耗尽导致的 OutOfMemoryError 时，解决方案很简单。应用程序只需要更多的空间来将所有的类加载到 PermGen 区域，所以我们只需要增加它的大小。为此，请更改您的应用程序启动配置，并添加(或增加，如果有的话)类似于以下示例的 **-XX:MaxPermSize** 参数:

    ```java
    java -XX:MaxPermSize=512m com.saket.demo.Permgen

    ```

4.  **Error 4 – Metaspace :** Java class metadata is allocated in native memory. If metaspace for class metadata is exhausted, a **java.lang.OutOfMemoryError** exception with a detail MetaSpace is thrown.
    The amount of metaspace that can be used for class metadata is limited by the parameter MaxMetaSpaceSize, which is specified on the command line. When the amount of native memory needed for a class metadata exceeds MaxMetaSpaceSize, a java.lang.OutOfMemoryError exception with a detail MetaSpace is thrown.

    ```java
    // Java program to illustrate
    // Metaspace error
    import java.util.*;

    public class Metaspace {
        static javassist.ClassPool cp = javassist.ClassPool.getDefault();

    public static void main(String args[]) throws Exception
        {
            for (int i = 0; i < 100000; i++) {
                Class c = cp.makeClass("com.saket.demo.Metaspace" + i).toClass();
            }
        }
    }
    ```

    这段代码将继续生成新的类，并将它们的定义加载到 Metaspace，直到空间被完全利用，并且抛出 Java . lang . out of memory error:Metaspace。当用-XX:MaxMetaspaceSize=64m 启动时，那么在 Mac OS X 上，我的 Java 1.8.0_05 在加载了大约 70，000 个类的情况下死亡。

    **预防:**如果已经在命令行上设置了 **MaxMetaSpaceSize** ，则增加其值。MetaSpace 是从与 Java 堆相同的地址空间分配的。减少 Java 堆的大小将为 MetaSpace 提供更多的可用空间。只有当 Java 堆中有多余的可用空间时，这才是正确的权衡。

5.  **Error 5 – Requested array size exceeds VM limit :** This error indicates that the application attempted to allocate an array that is larger than the heap size. For example, if an application attempts to allocate an array of 1024 MB but the maximum heap size is 512 MB then **OutOfMemoryError** will be thrown with “Requested array size exceeds VM limit”.

    ```java
    // Java program to illustrate
    // Requested array size
    // exceeds VM limit error
    import java.util.*;

    public class GFG {
        static List<String> list = new ArrayList<String>();

    public static void main(String args[]) throws Exception
        {
            Integer[] array = new Integer[10000 * 10000];
        }
    }
    ```

    请求的数组大小超过虚拟机限制可能是以下情况之一的结果:

    *   您的阵列变得太大，最终大小介于平台限制和整数之间。MAX_INT
    *   您故意尝试分配大于 2^31-1 元素的数组来试验极限。
6.  **Error 6 – Request size bytes for reason. Out of swap space? :** This apparent exception occurs when an allocation from the native heap failed and the native heap might be close to exhaustion. The error indicates the size (in bytes) of the request that failed and the reason for the memory request. Usually the reason is the name of the source module reporting the allocation failure, although sometimes it is the actual reason.
    **java.lang.OutOfMemoryError: Out of swap space** error is often caused by operating system level issues, such as:
    *   操作系统配置的交换空间不足。
    *   系统上的另一个进程正在消耗所有内存资源。

    **预防:**当抛出此错误消息时，VM 调用致命错误处理机制(即生成致命错误日志文件，其中包含崩溃时线程、进程和系统的有用信息)。在本机堆耗尽的情况下，日志中的堆内存和内存映射信息会很有用

7.  **Error 7 : reason stack_trace_with_native_method :** Whenever this error message(reason stack_trace_with_native_method) is thrown then a stack trace is printed in which the top frame is a native method, then this is an indication that a native method has encountered an allocation failure. The difference between this and the previous message is that the allocation failure was detected in a Java Native Interface (JNI) or native method rather than in the JVM code.

    ```java
    // Java program to illustrate
    // new native thread error
    import java.util.*;

    public class GFG {
    public static void main(String args[]) throws Exception
        {
            while (true) {
                new Thread(new Runnable()
                {
                    public void run()
                    {
                        try
                        {
                            Thread.sleep(1000000000);
            }
            catch (InterruptedException e)
            {
            }
        }
                }).start();
       }
      }
    }
    ```

    确切的本机线程限制取决于平台，例如，Mac OS X 的测试显示:

    **64 位 Mac OS X 10.9，Java 1 . 7 . 0 _ 45–JVM 在创建#2031 线程后死亡**

    **预防:**使用操作系统的本机实用程序进一步诊断问题。有关各种操作系统可用工具的更多信息，请参见[本地操作系统工具](https://docs.oracle.com/javase/8/docs/technotes/guides/troubleshoot/tooldescr020.html#BABBHHIE)。

**参考:**
[https://docs . Oracle . com/javase/8/docs/technotes/guides/疑难解答/memleaks002.html](https://docs.oracle.com/javase/8/docs/technotes/guides/troubleshoot/memleaks002.html)

本文由 **[Saket Kumar](https://www.facebook.com/saketkumar95)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。