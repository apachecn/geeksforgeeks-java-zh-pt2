# Java 中的 Stream mapToDouble()，示例

> 原文:[https://www . geesforgeks . org/stream-maptodouble-Java-examples/](https://www.geeksforgeeks.org/stream-maptodouble-java-examples/)

**Stream mapto double(to doublefunction mapper)**返回一个由给定函数应用于该流元素的结果组成的双流。

流映射器到双功能映射器(ToDoubleFunction mapper)是一个 ***中间操作*** 。这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。

**语法:**

```java
DoubleStream mapToDouble(ToDoubleFunction<**?** super **T**> mapper)

Where, A sequence of primitive double-valued
elements and T is the type of stream elements. 
mapper is a stateless function which is applied
to each element and the function returns the new stream.

```

**示例 1 :** mapToDouble()具有选择满足给定函数的元素的操作。

```java
// Java code for Stream mapToDouble
// (ToDoubleFunction mapper) to get a
// DoubleStream by applying the given function
// to the elements of this stream.
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a list of Strings
        List<String> list = Arrays.asList("10", "6.548", "9.12",
                                                    "11", "15");

        // Using Stream mapToDouble(ToDoubleFunction mapper)
        // and displaying the corresponding DoubleStream
        list.stream().mapToDouble(num -> Double.parseDouble(num))
                    .filter(num -> (num * num) * 2 == 450)
                    .forEach(System.out::println);
    }
}
```

输出:

```java
15.0

```

**示例 2 :** mapToDouble()具有返回字符串长度平方的流的操作。

```java
// Java code for Stream mapToDouble
// (ToDoubleFunction mapper) to get a
// DoubleStream by applying the given function
// to the elements of this stream.
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a list of Strings
        List<String> list = Arrays.asList("CSE", "JAVA", "gfg",
                                                    "C++", "C");

        // Using Stream mapToDouble(ToDoubleFunction mapper)
        // and displaying the corresponding DoubleStream
        // which contains square of length of each element in
        // given Stream
        list.stream().mapToDouble(str -> str.length() * str.length())
                     .forEach(System.out::println);
    }
}
```

输出:

```java
9.0
16.0
9.0
9.0
1.0

```