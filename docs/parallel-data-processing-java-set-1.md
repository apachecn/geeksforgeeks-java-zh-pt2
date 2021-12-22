# Java 中的并行数据处理|第 1 集

> 原文:[https://www . geesforgeks . org/parallel-data-processing-Java-set-1/](https://www.geeksforgeeks.org/parallel-data-processing-java-set-1/)

我们知道 Java 中新的[Stream](https://www.geeksforgeeks.org/stream-in-java/)(在 Java 8 中引入)接口让我们可以以声明的方式操作数据集合。
在本主题中，我们将发现 Stream 接口如何让我们有机会在不费力的情况下对数据集合并行执行操作。它允许我们声明性地将一个顺序流转换成一个并行流

**定义并制作成并行流:**
并行流是将元素拆分成多个流，并在不同线程上将它们分配成多个块的流。因此，我们可以在多处理器的核心上划分给定操作的工作负载，从而使 CPU 变得繁忙。我们可以通过附加关键字“parallel”将流转换为并行流。

下面的例子只是给了我们如何将一个流转换成一个并行流的想法！

```java
// A Simple Java program to demonstrate parallel
// processing.
import java.util.stream.*;
import java.util.Collections.*;
public class JavaApplication1 {

    static long sumparallel(long n)
    {
        // Stream converted to parallel stream 
        return Stream.iterate(1L, i->i + 1).
                       limit(n).parallel(). 
                       reduce(0L, Long::sum);
    }

    // Driver code
    public static void main(String[] args)
    {
        long c = sumparallel(10);
        System.out.println("Sum is " + c);
    }
}
```

输出:

```java
Sum is 55

```

在下一部分中，我们将看到并行流、顺序流和迭代过程之间的性能差异，并回顾并行流中某些更专业的方法。

 **参考:**

本文由 [**柯沙夫 _786**](https://auth.geeksforgeeks.org/profile.php?user=keshav_786) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。