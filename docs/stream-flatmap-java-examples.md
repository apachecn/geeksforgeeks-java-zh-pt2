# Java 中的 Stream flatMap()，带示例

> 原文:[https://www.geeksforgeeks.org/stream-flatmap-java-examples/](https://www.geeksforgeeks.org/stream-flatmap-java-examples/)

**Stream flatMap(函数映射器)**返回一个流，该流由用通过将提供的映射函数应用于每个元素而产生的映射流的内容替换该流的每个元素的结果组成。流平面图(功能映射器)是 ***中间操作*** 。这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。

**注意:**每个映射的流在其内容被放入该流后被关闭。如果映射的流为空，则改为使用空流。

**flat map()V/s[map()【T2:](https://www.geeksforgeeks.org/stream-map-java-examples/)**
1)[map()](https://www.geeksforgeeks.org/stream-map-java-examples/)取一条小溪，变换成另一条小溪。它对流的每个元素应用一个函数，并将返回值存储到新的流中。它不会使河流变平。但是 flatMap()是一个地图和一个平面操作的组合，也就是说，它对元素应用了一个函数，同时也把它们展平了。
2) [map()](https://www.geeksforgeeks.org/stream-map-java-examples/) 仅用于变换，但 flatMap()同时用于变换和展平。

**语法:**

```java
<**R**> Stream<**R**> flatMap(Function<**?** super T, **?** extends Stream<**?** extends R>> mapper)

where, R is the element type of the new stream.
Stream is an interface and T is the type 
of stream elements. mapper is a stateless function 
which is applied to each element and the function
returns the new stream.

```

**示例 1 :** 提供了映射功能的 flatMap()函数。

```java
// Java code for Stream flatMap
// (Function mapper) to get a stream by
// replacing the stream with a mapped
// stream by applying the provided mapping function.
import java.util.*;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a List of Strings
        List<String> list = Arrays.asList("5.6", "7.4", "4",
                                          "1", "2.3");

        // Using Stream flatMap(Function mapper)
        list.stream().flatMap(num -> Stream.of(num)).
                         forEach(System.out::println);
    }
}
```

输出:

```java
5.6
7.4
4
1
2.3

```

**示例 2 :** flatMap()函数提供了将字符串映射到位置 2 的操作。

```java
// Java code for Stream flatMap
// (Function mapper) to get a stream by
// replacing the stream with a mapped
// stream by applying the provided mapping function.
import java.util.*;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a List of Strings
        List<String> list = Arrays.asList("Geeks", "GFG",
                                 "GeeksforGeeks", "gfg");

        // Using Stream flatMap(Function mapper)
        list.stream().flatMap(str -> 
                         Stream.of(str.charAt(2))).
                         forEach(System.out::println);
    }
}
```

输出:

```java
e
G
e
g

```

###  **<center>flat map()是如何工作的？</center>

T3】**

正如在文章中已经讨论过的，flatMap()是一个地图和一个平面操作的组合，也就是说，它首先应用地图函数，然后将结果变平。让我们考虑一些例子来理解什么是流扁平化。
**例 1 :**
扁平化前的列表:

```java
[ [2, 3, 5], [7, 11, 13], [17, 19, 23] ]

```

该列表有 2 个级别，由 3 个小列表组成。扁平化后，转化为“一级”结构，如图所示:

```java
[ 2, 3, 5, 7, 11, 13, 17, 19, 23 ] 

```

**例 2 :**
拉平前的列表:

```java
[ ["G", "E", "E"], ["K", "S", "F"], ["O", "R", "G"], ["E", "E", "K", "S"] ]

```

该列表有 3 个级别，由 4 个小列表组成。扁平化后，转化为“一级”结构，如图所示:

```java
["G", "E", "E", "K", "S", "F", "O", "R", "G", "E", "E", "K", "S"] 

```

简而言之，我们可以说，如果在展平之前存在< < **数据类型** > > 的**列表流，那么在应用 flatMap()时，**数据类型<<**>>**的流在展平之后被返回。
**应用:******

```java
// Java code for Stream flatMap(Function mapper) 
import java.util.*;
import java.util.stream.Collectors;

class GFG
{   
    // Driver code
    public static void main(String[] args)
    {   
        // Creating a list of Prime Numbers
        List<Integer> PrimeNumbers = Arrays.asList(5, 7, 11,13);

        // Creating a list of Odd Numbers
        List<Integer> OddNumbers = Arrays.asList(1, 3, 5);

        // Creating a list of Even Numbers
        List<Integer> EvenNumbers = Arrays.asList(2, 4, 6, 8);

        List<List<Integer>> listOfListofInts =
                Arrays.asList(PrimeNumbers, OddNumbers, EvenNumbers);

        System.out.println("The Structure before flattening is : " +
                                                  listOfListofInts);

        // Using flatMap for transformating and flattening.
        List<Integer> listofInts  = listOfListofInts.stream()
                                    .flatMap(list -> list.stream())
                                    .collect(Collectors.toList());

        System.out.println("The Structure after flattening is : " +
                                                         listofInts);
    }
}
```

**输出:**

```java
The Structure before flattening is : [[5, 7, 11, 13], [1, 3, 5], [2, 4, 6, 8]]
The Structure after flattening is : [5, 7, 11, 13, 1, 3, 5, 2, 4, 6, 8] 
```