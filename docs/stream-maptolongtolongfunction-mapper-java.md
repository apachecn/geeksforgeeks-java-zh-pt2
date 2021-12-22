# Java 中的 Stream mapToLong()示例

> 哎哎哎:# t0]https://www . geeksforgeeks . org/stream-maptoolodlongfunction-mapper-Java/

**Stream mapToLong(ToLongFunction mapper)**返回一个 LongStream，该 LongStream 由给定函数应用于该流元素的结果组成。

流映射器(ToLongFunction mapper)是一个 ***中间操作*** 。这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。

**语法:**

```java
LongStream mapToLong(ToLongFunction<**?** super **T**> mapper)

Where, LongStream is a sequence of primitive 
long-valued elements and T is the type 
of stream elements. mapper is a stateless function 
which is applied to each element and the function
returns the new stream.

```

**例 1 :** mapToLong()函数，返回满足给定函数的流的操作。

```java
// Java code for Stream mapToLong
// (ToLongFunction mapper) to get a
// LongStream by applying the given function
// to the elements of this stream.
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        System.out.println("The stream after applying "
                        + "the function is : ");

        // Creating a list of Strings
        List<String> list = Arrays.asList("25", "225", "1000",
                                                  "20", "15");

        // Using Stream mapToLong(ToLongFunction mapper)
        // and displaying the corresponding LongStream
        list.stream().mapToLong(num -> Long.parseLong(num))
            .filter(num -> Math.sqrt(num) / 5 == 3 )
            .forEach(System.out::println);
    }
}
```

输出:

```java
The stream after applying the function is : 
225

```

**示例 2 :** 返回字符串长度中设定位数的 mapToLong()函数。

```java
// Java code for Stream mapToLong
// (ToLongFunction mapper) to get a
// LongStream by applying the given function
// to the elements of this stream.
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a list of Strings
        List<String> list = Arrays.asList("Data Structures", "JAVA", "OOPS",
                                             "GeeksforGeeks", "Algorithms");

        // Using Stream mapToLong(ToLongFunction mapper)
        // and displaying the corresponding LongStream
        // which contains the number of one-bits in 
        // binary representation of String length
        list.stream().mapToLong(str -> Long.bitCount(str.length()))
            .forEach(System.out::println);
    }
}
```

输出:

```java
4
1
1
3
2

```