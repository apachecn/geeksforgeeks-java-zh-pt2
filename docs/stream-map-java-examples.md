# Java 中的流图()，示例

> 原文:[https://www.geeksforgeeks.org/stream-map-java-examples/](https://www.geeksforgeeks.org/stream-map-java-examples/)

**流映射(函数映射器)**返回一个流，该流由给定函数应用于该流元素的结果组成。

流映射(功能映射器)是一个**中间操作**。这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。

**语法:**

```
<**R**> Stream<**R**> map(Function<**?** super **T**, **?** extends **R**> mapper)

where, R is the element type of the new stream.
Stream is an interface and T is the type 
of stream elements. mapper is a stateless function 
which is applied to each element and the function
returns the new stream.

```

**示例 1 :** 流映射()函数，对流的每个元素进行数字* 3 的运算。

```
// Java code for Stream map(Function mapper)
// to get a stream by applying the
// given function to this stream.
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        System.out.println("The stream after applying "
                           + "the function is : ");

        // Creating a list of Integers
        List<Integer> list = Arrays.asList(3, 6, 9, 12, 15);

        // Using Stream map(Function mapper) and
        // displaying the corresponding new stream
        list.stream().map(number -> number * 3).forEach(System.out::println);
    }
}
```

输出:

```
The stream after applying the function is : 
9
18
27
36
45

```

**例 2 :** 流映射()函数，具有将小写转换为大写的操作。

```
// Java code for Stream map(Function mapper)
// to get a stream by applying the
// given function to this stream.
import java.util.*;
import java.util.stream.Collectors;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        System.out.println("The stream after applying "
                           + "the function is : ");

        // Creating a list of Integers
        List<String> list = Arrays.asList("geeks", "gfg", "g",
                                          "e", "e", "k", "s");

        // Using Stream map(Function mapper) to
        // convert the Strings in stream to
        // UpperCase form
        List<String> answer = list.stream().map(String::toUpperCase).
        collect(Collectors.toList());

        // displaying the new stream of UpperCase Strings
        System.out.println(answer);
    }
}
```

输出:

```
The stream after applying the function is : 
[GEEKS, GFG, G, E, E, K, S]

```

**例 3 :** 流映射()函数，用映射字符串长度代替字符串的操作。

```
// Java code for Stream map(Function mapper)
// to get a stream by applying the
// given function to this stream.
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        System.out.println("The stream after applying "
                           + "the function is : ");

        // Creating a list of Strings
        List<String> list = Arrays.asList("Geeks", "FOR", "GEEKSQUIZ",
                                          "Computer", "Science", "gfg");

        // Using Stream map(Function mapper) and
        // displaying the length of each String
        list.stream().map(str -> str.length()).forEach(System.out::println);
    }
}
```

输出:

```
The stream after applying the function is : 
5
3
9
8
7
3

```