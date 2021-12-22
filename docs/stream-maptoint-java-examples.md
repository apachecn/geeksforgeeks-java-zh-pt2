# Java 中的流映射(带示例)

> 原文:[https://www . geesforgeks . org/stream-maptoint-Java-examples/](https://www.geeksforgeeks.org/stream-maptoint-java-examples/)

**流映射函数映射器(ToIntFunction mapper)** 返回一个包含给定函数应用于该流元素的结果的输入流。

流映射是一个**的中间操作。这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。**

****语法:****

```
**IntStream mapToInt(ToIntFunction<**?** super **T**> mapper)**

Where, IntStream is a sequence of primitive 
int-valued elements and T is the type 
of stream elements. mapper is a stateless function 
which is applied to each element and the function
returns the new stream. 
```

****示例 1 :** mapToInt()具有打印流元素的操作，如果可被 3 整除。**

```
// Java code for Stream mapToInt
// (ToIntFunction mapper) to get a
// IntStream by applying the given function
// to the elements of this stream.
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a list of Strings
        List<String> list = Arrays.asList("3", "6", "8", 
                                            "14", "15");

        // Using Stream mapToInt(ToIntFunction mapper)
        // and displaying the corresponding IntStream
        list.stream().mapToInt(num -> Integer.parseInt(num))
                     .filter(num -> num % 3 == 0)
                     .forEach(System.out::println);
    }
}
```

**输出:**

```
3
6
15 
```

****例 2 :** mapToInt()执行映射字符串及其长度的操作后返回 IntStream。**

```
// Java code for Stream mapToInt
// (ToIntFunction mapper) to get a
// IntStream by applying the given function
// to the elements of this stream.
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a list of Strings
        List<String> list = Arrays.asList("Geeks", "for", "gfg",
                                          "GeeksforGeeks", "GeeksQuiz");

        // Using Stream mapToInt(ToIntFunction mapper)
        // and displaying the corresponding IntStream
        // which contains length of each element in
        // given Stream
        list.stream().mapToInt(str -> str.length()).forEach(System.out::println);
    }
}
```

**输出:**

```
5
3
3
13
9 
```