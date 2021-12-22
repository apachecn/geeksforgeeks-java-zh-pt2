# Java 中的 Stream forEachOrdered()方法，带示例

> 原文:[https://www . geeksforgeeks . org/stream-foreachordered-method-Java-examples/](https://www.geeksforgeeks.org/stream-foreachordered-method-java-examples/)

**流 forEachOrdered(消费者动作)**如果流具有定义的相遇顺序，则按照流的相遇顺序为该流的每个元素执行一个动作。流 forEachOrdered(消费者行为)是一种 ***终端操作*** ，即它可能穿越流以产生结果或副作用。

**语法:**

```
void forEachOrdered(Consumer<**?** super T> action)

Where, Consumer is a functional interface which 
is expected to operate via side-effects. and T 
is the type of stream elements.

```

**注意:**该操作一次处理一个元素，如果存在元素，则按遇到顺序处理。对一个元素执行操作发生在对后续元素执行操作之前。

**例 1 :** 按原顺序打印整数数组的元素。

```
// Java code for forEachOrdered
// (Consumer action) in Java 8
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args) {

    // Creating a list of Integers
    List<Integer> list = Arrays.asList(10, 19, 20, 1, 2);

    // Using forEachOrdered(Consumer action) to 
    // print the elements of stream in encounter order
    list.stream().forEachOrdered(System.out::println);

}
}
```

**Output:**

```
10
19
20
1
2

```

**例 2 :** 按原顺序打印字符串数组的元素。

```
// Java code for forEachOrdered
// (Consumer action) in Java 8
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args) {

    // Creating a list of Strings
    List<String> list = Arrays.asList("GFG", "Geeks", 
                             "for", "GeeksforGeeks");

    // Using forEachOrdered(Consumer action) to 
    // print the elements of stream in encounter order
    list.stream().forEachOrdered(System.out::println);

}
}
```

**Output:**

```
GFG
Geeks
for
GeeksforGeeks

```

**示例 3 :** 按原始顺序打印字符串数组索引 2 处的字符。

```
// Java code for forEachOrdered
// (Consumer action) in Java 8
import java.util.*;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args) {

    // Creating a Stream of Strings
    Stream<String> stream = Stream.of("GFG", "Geeks", 
                             "for", "GeeksforGeeks");

    // Using forEachOrdered(Consumer action) 
    stream.flatMap(str-> Stream.of(str.charAt(2)))
          .forEachOrdered(System.out::println);

}
}
```

**Output:**

```
G
e
r
e

```