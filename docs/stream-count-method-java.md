# Java 中的流计数()方法，带示例

> 原文:[https://www.geeksforgeeks.org/stream-count-method-java/](https://www.geeksforgeeks.org/stream-count-method-java/)

**long count()** 返回流中元素的计数。这是 ***约简*** 的一个特例(约简操作取一系列输入元素，通过重复应用一个组合操作，将它们组合成单个汇总结果)。这是一个 ***终端操作*** ，也就是说，它可能穿越这个流产生一个结果或者一个副作用。执行终端操作后，流管道被认为已消耗，不能再使用。

**语法:**

```
long count()

```

**注意:**count 操作的返回值是流中元素的计数。

**例 1 :** 计算数组中元素的个数。

```
// Java code for Stream.count()
// to count the elements in the stream.
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // creating a list of Integers
        List<Integer> list = Arrays.asList(0, 2, 4, 6,
                                           8, 10, 12);

        // Using count() to count the number
        // of elements in the stream and
        // storing the result in a variable.
        long total = list.stream().count();

        // Displaying the number of elements
        System.out.println(total);
    }
}
```

输出:

```
7

```

**示例 2 :** 计算列表中不同元素的数量。

```
// Java code for Stream.count()
// to count the number of distinct
// elements in the stream.
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // creating a list of Strings
        List<String> list = Arrays.asList("GFG", "Geeks", "for", "Geeks",
                                          "GeeksforGeeks", "GFG");

        // Using count() to count the number
        // of distinct elements in the stream and
        // storing the result in a variable.
        long total = list.stream().distinct().count();

        // Displaying the number of elements
        System.out.println(total);
    }
}
```

输出:

```
4

```