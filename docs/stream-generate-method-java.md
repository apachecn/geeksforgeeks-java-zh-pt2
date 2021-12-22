# Java 中的 Stream generate()方法，示例

> 原文:[https://www.geeksforgeeks.org/stream-generate-method-java/](https://www.geeksforgeeks.org/stream-generate-method-java/)

**流生成(供应商< **T** > s)** 返回一个无限顺序无序流，其中每个元素都由提供的供应商生成。这适用于生成恒定流、随机元素流等。

**语法:**

```
static <T> Stream<T> generate(Supplier<T> s)

Where, Stream is an interface and T
is the type of stream elements.
s is the Supplier of generated 
elements and the return value is
a new infinite sequential
unordered Stream.

```

**示例 1 :** 生成随机整数流。

```
// Java code for Stream.generate()
// to generate an infinite sequential
// unordered stream
import java.util.*;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args) {

    // using Stream.generate() method 
    // to generate 5 random Integer values
    Stream.generate(new Random()::nextInt)
    .limit(5).forEach(System.out::println); 
    }
}
```

输出:

```
697197501
50139200
321540264
1042847655
-770409472

```

**示例 2 :** 生成随机 Double 流。

```
// Java code for Stream.generate()
// to generate an infinite sequential
// unordered stream
import java.util.*;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args) {

    // using Stream.generate() method 
    // to generate 8 random Double values
    Stream.generate(new Random()::nextDouble)
    .limit(8).forEach(System.out::println); 
    }
}
```

输出:

```
0.5390254520295368
0.8477297185718798
0.23703352435894398
0.09156832989674057
0.9671295321757734
0.9989670394813547
0.8909416330715489
0.08177639888829968

```