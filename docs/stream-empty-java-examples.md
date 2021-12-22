# Java 中的空()流，示例

> 原文:[https://www.geeksforgeeks.org/stream-empty-java-examples/](https://www.geeksforgeeks.org/stream-empty-java-examples/)

**流空()**创建一个空的顺序流。

**语法:**

```
static <T> Stream<T> empty()

```

**参数:**

*   **t:** Type of flow element.
*   **[stream](https://www.geeksforgeeks.org/stream-in-java/) :** An object sequence that supports various methods that can be pipelined to produce desired results.

**返回值:** Stream empty()返回一个空的顺序流。

**注意:**在用流参数调用方法时，空流可能有助于避免空指针异常。

**例:**

```
// Java code for Stream empty()
import java.util.*;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an empty Stream
        Stream<String> stream = Stream.empty();

        // Displaying elements in Stream
        stream.forEach(System.out::println);
    }
}
```

输出:

```
No Output

```