# Java 中的 Stream flatMapToDouble()，示例

> 原文:[https://www . geeksforgeeks . org/stream-flat maptodouble-Java-examples/](https://www.geeksforgeeks.org/stream-flatmaptodouble-java-examples/)

**Stream flatMapToDouble(函数映射器)**返回一个 DoubleStream，该 double Stream 由将提供的映射函数应用于每个元素而产生的映射流的内容替换该流的每个元素的结果组成。流平面映射器是一个 ***中间操作*** 。这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。

**注意:**每个映射的流在其内容被放入该流后被关闭。如果映射的流为空，则改为使用空流。
**语法:**

```
DoubleStream flatMapToDouble(Function<**?** super T, **?** extends DoubleStream> mapper)

Where, DoubleStream is a sequence of primitive
double-valued elements and T is the type 
of stream elements. mapper is a stateless function 
which is applied to each element and the function
returns the new stream.

```

**示例 1:**flatmaptooDouble()函数，带有解析字符串为 double 的操作。

```
// Java code for Stream flatMapToDouble
// (Function mapper) to get an DoubleStream
// consisting of the results of replacing
// each element of this stream with the
// contents of a mapped stream.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a list of Strings
        List<String> list = Arrays.asList("1.5", "2.7", "3",
                                                "4", "5.6");

        // Using Stream flatMapToDouble(Function mapper)
        list.stream().flatMapToDouble(num 
        -> DoubleStream.of(Double.parseDouble(num)))
        .forEach(System.out::println);
    }
}
```

输出:

```
1.5
2.7
3.0
4.0
5.6

```

**示例 2 :** flatMapToDouble()函数，具有返回字符串长度的流的操作。

```
// Java code for Stream flatMapToDouble
// (Function mapper) to get an DoubleStream
// consisting of the results of replacing
// each element of this stream with the
// contents of a mapped stream.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a List of Strings
        List<String> list = Arrays.asList("Geeks", "GFG",
                                 "GeeksforGeeks", "gfg");

        // Using Stream flatMapToDouble(Function mapper)
        // to get length of all strings present in list
        list.stream().flatMapToDouble(str 
        -> DoubleStream.of(str.length()))
        .forEach(System.out::println);
    }
}
```

输出:

```
5.0
3.0
13.0
3.0

```