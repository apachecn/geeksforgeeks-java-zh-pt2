# Java 中的 System.exit()

> 原文:[https://www.geeksforgeeks.org/system-exit-in-java/](https://www.geeksforgeeks.org/system-exit-in-java/)

**java.lang.System.exit()** 方法通过终止正在运行的 java 虚拟机退出当前程序。此方法采用状态代码。状态码的非零值通常用于指示异常终止。这类似于 C/C++ 中的[退出。](https://www.geeksforgeeks.org/understanding-exit-abort-and-assert/)

以下是 **java.lang.System.exit()** 方法的声明:

```java
public static void exit(int status)
```

**退出(0)** :一般用于表示成功终止。
**退出(1)或退出(-1)或任何其他非零值**–通常表示终止不成功。

**注意:**此方法不返回值。

下面的例子展示了 **java.lang.System.exit()** 方法的用法。

```java
// A Java program to demonstrate working of exit()
import java.util.*;
import java.lang.*;

class GfG
{
    public static void main(String[] args)
    {
        int arr[] = {1, 2, 3, 4, 5, 6, 7, 8};

        for (int i = 0; i < arr.length; i++)
        {
            if (arr[i] >= 5)
            {
                System.out.println("exit...");

                // Terminate JVM
                System.exit(0);
            }
            else
                System.out.println("arr["+i+"] = " +
                                  arr[i]);
        }
        System.out.println("End of Program");
    }
}
```

输出:

```java
arr[0] = 1
arr[1] = 2
arr[2] = 3
arr[3] = 4
exit...

```

**参考:**
[https://docs . Oracle . com/javase/7/docs/API/Java/lang/runtime . html](https://docs.oracle.com/javase/7/docs/api/java/lang/Runtime.html)

本文由**阿米特·坎德尔瓦尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。