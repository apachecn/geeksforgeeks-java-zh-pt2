# Java 中 JVM 垃圾收集器的类型及实现细节

> 原文:[https://www . geesforgeks . org/type-of-JVM-垃圾收集器-in-Java-with-implementation-details/](https://www.geeksforgeeks.org/types-of-jvm-garbage-collectors-in-java-with-implementation-details/)

**先决条件:** [垃圾收集](https://www.geeksforgeeks.org/garbage-collection-java)[标记和清除算法](https://www.geeksforgeeks.org/mark-and-sweep-garbage-collection-algorithm/)

**[垃圾收集](https://www.geeksforgeeks.org/garbage-collection-java/) :** 垃圾收集又名 GC 是 Java 最[的重要特性之一。垃圾收集是 Java 中用于取消分配未使用内存的机制，它只是清除未使用对象消耗的空间。为了释放未使用的内存，垃圾收集器跟踪所有仍在使用的对象，并将对象的其余部分标记为垃圾。基本上垃圾收集器使用](https://www.geeksforgeeks.org/java-how-to-start-learning-java/)[标记和清除算法](https://www.geeksforgeeks.org/mark-and-sweep-garbage-collection-algorithm/)来清除未使用的内存。

<u>**垃圾收集类型** :</u>

[JVM](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/) 实际上提供了四种不同的垃圾收集器。每个垃圾收集器在应用程序吞吐量和应用程序暂停方面都会有所不同。应用程序吞吐量表示 Java 应用程序运行的速度，应用程序暂停表示垃圾收集器清理未使用的内存空间所花费的时间。

1.  **Serial Garbage Collector**: This is the simplest GC implementation, as it basically works with a single thread. If we select Serial garbage collector as our default garbage collector then whenever we will call garbage collector to clean unused memory then serial garbage collector holds all the running threads of application i.e. It works by freezing all the application threads and It will create a single thread to perform garbage collection. It freezes all other running threads of application until garbage collection operations have concluded. If we use Serial Garbage Collector as our default garbage collector then the application throughput will decrease and application pause time will increase. As a result, this GC implementation freezes all application threads when it runs. Hence, it is not a good idea to use it in multi-threaded applications like server environments.

    **实现:**
    如果要使用串口垃圾收集器，那么我们就要在运行 jar 的时候明确提到像:

    > Java-xx:+useserialcc-jar gfgapplicationjar . Java

2.  **并行垃圾收集器**:并行垃圾收集器是 Java 8 中默认的垃圾收集器。它也被称为**吞吐量收集器**。并行垃圾收集器与串行垃圾收集器相同，因为并行垃圾收集器在执行垃圾收集时还会冻结应用程序的运行线程。但不同的是，并行垃圾收集器使用多个线程来清理未使用的堆区域。使用垃圾收集器作为默认垃圾收集器的优势在于，我们可以提到垃圾收集器的一些属性，例如
    *   How many threads, can garbage collector use to perform garbage collection.

        **实施:**

        > Java-xx:+useparallel GC-xx:parallel gcthreads =**numeroftthreads**-jar gfgapplicationjar . Java

    *   Maximum pause can garbage collector take while performing garbage collection

        **实施:**

        > Java-xx:+useparallel GC-xx:maxgcpausemilis =**secinillsecond**-jar gfgapplicationjar . Java

并行垃圾收集器比串行垃圾收集器好得多，但是并行垃圾收集器的一个问题是，它在次要操作期间也会暂停应用程序。如果能够处理这种暂停的应用程序，它是最适合的。如果我们使用 JDK 8，那么并行垃圾收集器是默认的。

**实现:**如果我们在 java 9 上运行，并且想要使用并行垃圾收集器，那么我们应该使用下面的命令:

> Java-xx:+useparallel GC-jar gfgapplicationjar . Java

6.  **CMS Garbage collector**: CMS Garbage collector is known as [concurrent mark-sweep garbage collector](https://www.geeksforgeeks.org/mark-and-sweep-garbage-collection-algorithm/). This garbage collector uses multiple threads to scan the heap memory consistently to the mark objects that are unused and then sweep the marked objects. As we know, Serial garbage collector and Parallel garbage collector freeze the running threads of the application while performing the garbage collection. But CMS Garbage collector will perform freezing of running threads i.e. application pause in two cases only:
    *   在执行垃圾收集时，如果并行堆内存发生变化。
    *   同时在旧的生成空间中标记被引用的对象。

    如果我们将 CMS 收集器与 Parallel 垃圾收集器进行比较，CMS 收集器会使用更多的 CPU 来确保更好的应用程序吞吐量。如果我们正在开发一个可以提供更多 CPU 资源以获得更好性能的应用程序，那么 CMS 垃圾收集器是块优先于并行收集器的选择。要启用内容管理系统垃圾收集器，我们可以使用以下参数:

    > Java-xx:+useparnewgc-jar gfgapplicationjar . Java

7.  **G1 Garbage Collector**: Firstly G1 Garbage Collector is introduced in JDK 7\. Initially, It was designed to provide better support for larger heap memory application. G1 Garbage Collector is the default garbage collection of Java 9\. G1 collector replaced the CMS collector since it’s more performance efficient. How G1 Garbage Collector works is different from other collectors. Unlike other collectors, the G1 collector partitions the heap space into multiple equal-sized regions. Basically it is mainly designed for an application having heap size greater than 4GB. It divides the heap area into multiple regions vary from 1MB to 32MB. While performing the garbage collection, G1 Garbage Collector mark the heap region which has objects that are in use throughout the heap. By the help of this garbage collector has the information about the regions that contains most use less objects and garbage collector first perform the garbage collection on that region only. Thats why it is known as G first garbage collector. G1 also does compact the free heap space just after garbage collection that makes G1 Garbage Collector better than other garbage collectors. G1 Garbage Collector is the default garbage collector of Java 9.

    **实现:**如果我们使用的是低于 9 的 Java 版本，并且我们想要使用 G1 垃圾收集器，那么我们必须在运行 jar 文件时明确提到，比如:

    > Java-xx:+useg1 GC-jar gfgapplicationjar . Java