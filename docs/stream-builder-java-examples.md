# Java 中的流构建器()，示例

> 原文:[https://www.geeksforgeeks.org/stream-builder-java-examples/](https://www.geeksforgeeks.org/stream-builder-java-examples/)

**流构建器()**返回一个流的构建器。

**语法:**

```
static <T> Stream.Builder<T> builder()

where, T is the type of elements.

```

**返回值:**一个流构建器。

**例 1 :**

```
// Java code for Stream builder()
import java.util.*;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Using Stream builder()
        Stream.Builder<String> builder = Stream.builder();

        // Adding elements in the stream of Strings
        Stream<String> stream = builder.add("Geeks").build();

        // Displaying the elements in the stream
        stream.forEach(System.out::println);
    }
}
```

输出:

```
Geeks

```

**例 2 :**

```
// Java code for Stream builder()
import java.util.*;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Using Stream builder()
        Stream.Builder<String> builder = Stream.builder();

        // Adding elements in the stream of Strings
        Stream<String> stream = builder.add("Geeks")
                                    .add("for")
                                    .add("Geeks")
                                    .add("GeeksQuiz")
                                    .build();

        // Displaying the elements in the stream
        stream.forEach(System.out::println);
    }
}
```

输出:

```
Geeks
for
Geeks
GeeksQuiz

```

**例 3 :**

```
// Java code for Stream builder()
import java.util.*;
import java.util.stream.Stream;
import java.util.stream.Collectors;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Using Stream builder()
        Stream.Builder<String> builder = Stream.builder();

        // Adding elements in the stream of Strings
        Stream<String> stream = builder.add("GEEKS")
                                    .add("for")
                                    .add("Geeks")
                                    .add("GeEKSQuiz")
                                    .build();

        // Converting elements to Lower Case
        // and storing them in List list
        List<String> list = stream.map(String::toLowerCase)
                                .collect(Collectors.toList());

        // Displaying the elements in list
        System.out.println(list);
    }
}
```

输出:

```
[geeks, for, geeks, geeksquiz]

```