# Java 中的 Stream flatMapToLong()示例

> 原文:[https://www . geesforgeks . org/stream-flatmaptolong-Java-examples/](https://www.geeksforgeeks.org/stream-flatmaptolong-java-examples/)

**Stream flatMapToLong(函数映射器)**将给定的映射器函数应用于流的每个元素，并返回一个 LongStream。流平面映射器(功能映射器)是 ***中间操作*** 。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。

**注意:**每个映射的流在其内容被放入该流后被关闭。如果映射的流为空，则改为使用空流。
**语法:**

```
LongStream flatMapToLong(Function<**?** super T, **?** extends LongStream> mapper)

Where, LongStream is a sequence of primitive
long-valued elements and T is the type 
of stream elements. mapper is a stateless function 
which is applied to each element and the function
returns the new stream.

```

**例 1 :** flatMapToLong()的解析字符串操作为 Long。

```
// Java code for Stream flatMapToLong
// (Function mapper) to get an LongStream
// consisting of the results of replacing
// each element of this stream with the
// contents of a mapped stream.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a list of Strings
        List<String> list = Arrays.asList("1", "2", "3",
                                          "4", "5");

        // Using Stream flatMapToLong(Function mapper)
        list.stream().flatMapToLong(num -> 
                     LongStream.of(Long.parseLong(num))).
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

**例 2 :** flatMapToLong()带有字符串长度映射字符串的操作。

```
// Java code for Stream flatMapToLong
// (Function mapper) to get an LongStream
// consisting of the results of replacing
// each element of this stream with the
// contents of a mapped stream.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a List of Strings
        List<String> list = Arrays.asList("Geeks", "GFG",
                                 "GeeksforGeeks", "gfg");

        // Using Stream flatMapToLong(Function mapper)
        // to get length of all strings present in list
        list.stream().flatMapToLong(str -> 
                        LongStream.of(str.length())).
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

**例 3 :** flatMapToLong()函数，具有返回流的操作。

```
// Java code for Stream mapToLong
// (ToLongFunction mapper) to get a
// LongStream by applying the given function
// to the elements of this stream.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a list of Strings
        List<String> list = Arrays.asList("5.36","27.9",
                                         "3","4.2","5");

        // Using Stream mapToLong(ToLongFunction mapper)
        // and displaying the corresponding LongStream
        list.stream().flatMapToLong(n
                     -> LongStream.of(Long.parseLong(n)) )
                     .forEach(System.out::println);
    }
}
```

输出:

```
Exception in thread "main" java.lang.NumberFormatException: For input string: "5.36"

```

**注意:**一个 Java***numberformateexception***通常发生在你试图把一个字符串转换成一个数值的时候，比如 int、float、double、long 等等。