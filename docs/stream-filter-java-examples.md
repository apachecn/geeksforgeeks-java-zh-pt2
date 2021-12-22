# Java 中的流过滤器()，示例

> 原文:[https://www.geeksforgeeks.org/stream-filter-java-examples/](https://www.geeksforgeeks.org/stream-filter-java-examples/)

**流过滤器(谓词谓词)**返回一个由该流中与给定谓词匹配的元素组成的流。这是一个 ***的中级操作。*** 这些操作总是懒惰的，即执行诸如 filter()的中间操作实际上并不执行任何过滤，而是创建一个新的流，当遍历该流时，它包含与给定谓词匹配的初始流的元素。

**语法:**

```java
Stream<**T**> filter(Predicate<**?** super **T**> predicate)

Where, Stream is an interface and T is the 
type of the input to the predicate.
The function returns the new stream.

```

**示例 1 :** 过滤()方法，具有过滤掉可被 5 整除的元素的操作。

```java
// Java code for Stream filter
// (Predicate predicate) to get a stream
// consisting of the elements of this
// stream that match the given predicate.
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a list of Integers
        List<Integer> list = Arrays.asList(3, 4, 6, 12, 20);

        // Using Stream filter(Predicate predicate)
        // to get a stream consisting of the
        // elements that are divisible by 5
        list.stream().filter(num -> num % 5 == 0).forEach(System.out::println);
    }
}
```

输出:

```java
20

```

**示例 2 :** filter()方法，操作是过滤掉索引 1 处带有大写字母的元素。

```java
// Java code for Stream filter
// (Predicate predicate) to get a stream
// consisting of the elements of this
// stream that match the given predicate.
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a Stream of Strings
        Stream<String> stream = Stream.of("Geeks", "fOr",
                                          "GEEKSQUIZ", "GeeksforGeeks");

        // Using Stream filter(Predicate predicate)
        // to get a stream consisting of the
        // elements having UpperCase Character
        // at index 1
        stream.filter(str -> Character.isUpperCase(str.charAt(1)))
            .forEach(System.out::println);
    }
}
```

输出:

```java
fOr
GEEKSQUIZ

```

**示例 3 :** 过滤()方法，过滤掉以 s 结尾的元素

```java
// Java code for Stream filter
// (Predicate predicate) to get a stream
// consisting of the elements of this
// stream that match the given predicate.
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a Stream of Strings
        Stream<String> stream = Stream.of("Geeks", "foR",
                                          "GeEksQuiz", "GeeksforGeeks");

        // Using Stream filter(Predicate predicate)
        // to get a stream consisting of the
        // elements ending with s
        stream.filter(str -> str.endsWith("s"))
            .forEach(System.out::println);
    }
}
```

输出:

```java
Geeks
GeeksforGeeks

```