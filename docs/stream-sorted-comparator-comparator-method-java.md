# Java 中的流排序(比较器比较器)方法

> 原文:[https://www . geesforgeks . org/stream-sorted-comparator-method-Java/](https://www.geeksforgeeks.org/stream-sorted-comparator-comparator-method-java/)

**流排序(比较器比较器)**返回由该流的元素组成的流，根据比较器提供的**进行排序。对于有序流，排序方法是稳定的，但是对于无序流，不保证稳定性。这是一个 ***有状态的中间操作*** ，也就是说，当处理新元素时，它可以合并来自先前看到的元素的状态。在 java 8 中，比较器可以使用[λ表达式](https://www.geeksforgeeks.org/lambda-expressions-java-8/)进行实例化。我们也可以颠倒自然排序以及比较器提供的排序。
**语法:****

```java
Stream<T> sorted(Comparator<? super T> comparator)

Where, Stream is an interface and T
is the type of stream elements.
comparator is used to compare stream elements.

```

下面给出了一些例子，以便更好地理解函数的实现。

**例 1 :**

```java
// Implementation of Stream.sorted()
// to get a stream of sorted elements
// according to the provided Comparator
import java.util.*;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a list of Integers
        List<Integer> list = Arrays.asList(5, -10, 7, -18, 23);

        System.out.println("The sorted stream according "
                           + "to provided Comparator is : ");

        // Displaying the list of Strings in
        // reverse order after sorting
        list.stream().sorted(Comparator.reverseOrder()).
                          forEach(System.out::println);
    }
}
```

输出:

```java
The sorted stream according to provided Comparator is : 
23
7
5
-10
-18

```

**例 2 :**

```java
// Implementation of Stream.sorted()
// to get a stream of sorted elements
// according to the provided Comparator
import java.util.*;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a list of Strings
        List<String> list = Arrays.asList("Geeks", "for",
                    "GeeksforGeeks", "GeeksQuiz", "GFG");

        System.out.println("The sorted stream according "
                           + "to provided Comparator is : ");

        // Displaying the list of Strings in
        // reverse order after sorting
        list.stream().sorted(Comparator.reverseOrder()).
                            forEach(System.out::println);
    }
}
```

输出:

```java
The sorted stream according to provided Comparator is : 
for
GeeksforGeeks
GeeksQuiz
Geeks
GFG

```

**例 3 :**

```java
// Implementation of Stream.sorted()
// to get a stream of sorted elements
import java.util.*;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating an array of Strings
        String[] array = { "GFG", "Geeks", "for",
                           "GeeksforGeeks", "GeeksQuiz" };

        System.out.println("The sorted stream is :");

        // sorting the elements of array based
        // on their last character
        Stream.of(array).sorted((str1, str2)
                     -> Character.compare(str1
                     .charAt(str1.length() - 1),
                    str2.charAt(str2.length() - 1)))
            .         forEach(System.out::println);
    }
}
```

输出:

```java
The sorted stream is :
GFG
for
Geeks
GeeksforGeeks
GeeksQuiz

```