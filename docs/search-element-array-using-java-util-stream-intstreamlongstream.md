# Java . util . stream . int stream/LongStream |搜索元素

> 原文:[https://www . geeksforgeeks . org/search-element-array-using-Java-util-stream-intstreaming stream/](https://www.geeksforgeeks.org/search-element-array-using-java-util-stream-intstreamlongstream/)

给定一个整数或长数据类型的元素数组，您需要使用**Java . util . stream . int stream**中的预定义函数检查该数组中是否存在给定的键。Java . util . stream . int stream/LongStream 类包含一个函数 anyMatch()，它有助于检查数组中是否存在特定的元素。

示例:

```java
Input : arr[] = {1,2,3,4,5,6,7} ,  key = 3
Output : Yes
         3 is present in the array.

Input : arr[] = {1,2,3,4,5,6,7} ,  key = 8
Output : No

```

**Stream.anyMatch()** 方法用于检查流中是否包含任何与给定谓词匹配的元素。如果流中至少有 1 个元素与给定的谓词条件匹配，则返回 true，否则返回 false。
语法:

```java
boolean anyMatch(Predicate< ? super T >  predicate)

```

下面是一个关于如何对整数流和长整数流使用 anyMatch()方法的 Java 程序。

```java
// Java program to check if an element is present
// in an array using java.util.stream.IntStream

import java.util.stream.IntStream;
import java.util.stream.LongStream;

class CheckElement
{
    public static void main (String[] args) 
    {   
        // stream of integer
        int num[] = {1,2,3,4,5,6,7};

        int key = 3;  // key to be searched
        boolean result = IntStream.of(num).anyMatch(x -> x == key);
        if (result)
            System.out.println("Yes");
        else
            System.out.println("No");

        // stream of long
        long lnum[] = {1,2,3,4,5,6,7};

        // key to be searched
        long lkey = 7;
        boolean result2 = LongStream.of(lnum).anyMatch(x -> x == lkey);
        if (result2)
            System.out.println("Yes");
        else
            System.out.println("No");
    }
}
```

输出:

```java
Yes
Yes

```

**参考** : [anyMatch() java 文档](https://docs.oracle.com/javase/8/docs/api/java/util/stream/Stream.html#anyMatch-java.util.function.Predicate-)

本文由**阿卡什·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。