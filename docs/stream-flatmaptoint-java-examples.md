# Java 中的 Stream flatMapToInt()，示例

> 原文:[https://www . geesforgeks . org/stream-flatmaptoit-Java-examples/](https://www.geeksforgeeks.org/stream-flatmaptoint-java-examples/)

**Stream flatmaptoit(函数映射器)**返回一个 IntStream，该 int Stream 由将提供的映射函数应用于每个元素而产生的映射流的内容替换该流的每个元素的结果组成。流平面映射是一个 ***中间操作*** 。这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。

**注意:**每个映射的流在其内容被放入该流后被关闭。如果映射的流为空，则改为使用空流。
**语法:**

```
IntStream flatMapToInt(Function<**?** super T, **?** extends IntStream> mapper)

Where, IntStream is a sequence of primitive 
int-valued elements and T is the type 
of stream elements. mapper is a stateless function 
which is applied to each element and the function
returns the new stream.

```

**示例 1:**flatmaptoit()函数，具有将字符串解析为整数的操作。

```
// Java code for Stream flatMapToInt
// (Function mapper) to get an IntStream
// consisting of the results of replacing
// each element of this stream with the
// contents of a mapped stream.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a list of Strings
        List<String> list = Arrays.asList("1", "2", "3",
                                          "4", "5");

        // Using Stream flatMapToInt(Function mapper)
        list.stream().flatMapToInt(num -> IntStream.of(Integer.parseInt(num))).
        forEach(System.out::println);
    }
}
```

输出:

```
1
2
3
4
5

```

**示例 2:**flatmaptoit()函数，操作映射字符串及其长度。

```
// Java code for Stream flatMapToInt
// (Function mapper) to get an IntStream
// consisting of the results of replacing
// each element of this stream with the
// contents of a mapped stream.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a List of Strings
        List<String> list = Arrays.asList("Geeks", "GFG",
                                          "GeeksforGeeks", "gfg");

        // Using Stream flatMapToInt(Function mapper)
        // to get length of all strings present in list
        list.stream().flatMapToInt(str -> IntStream.of(str.length())).
        forEach(System.out::println);
    }
}
```

输出:

```
5
3
13
3

```