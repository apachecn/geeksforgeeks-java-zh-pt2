# 流排序()在 Java 中

> 原文:[https://www.geeksforgeeks.org/stream-sorted-in-java/](https://www.geeksforgeeks.org/stream-sorted-in-java/)

**Stream sorted()** 返回一个由这个流的元素组成的流，按照自然顺序排序。对于有序流，排序方法是稳定的，但是对于无序流，不保证稳定性。这是一个**有状态的中间操作**，也就是说，当处理新的元素时，它可以包含来自以前看到的元素的状态。

**语法:**

```
Stream<T> sorted()

Where, Stream is an interface and T
is the type of stream elements.

```

**异常:**如果该流的元素不可比较，则在执行终端操作时可能会抛出***Java . lang . class castexception***。

下面给出了一些例子，以便更好地理解函数的实现。

**例 1 :**

```
// Implementation of Stream.sorted()
// to get a stream of elements
// sorted in their natural order
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a list of integers
        List<Integer> list = Arrays.asList(-9, -18, 0, 25, 4);

        System.out.println("The sorted stream is : ");

        // displaying the stream with elements
        // sorted in natural order
        list.stream().sorted().forEach(System.out::println);
    }
}
```

**Output:**

```
The sorted stream is : 
-18
-9
0
4
25

```

**例 2 :**

```
// Implementation of Stream.sorted()
// to get a stream of elements
// sorted in their natural order
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a list of strings
        List<String> list = Arrays.asList("Geeks", "for",
                     "GeeksQuiz", "GeeksforGeeks", "GFG");

        System.out.println("The sorted stream is : ");

        // displaying the stream with elements
        // sorted in their natural order
        list.stream().sorted().forEach(System.out::println);
    }
}
```

**Output:**

```
The sorted stream is : 
GFG
Geeks
GeeksQuiz
GeeksforGeeks
for

```

**例 3 :**

```
// Using stream sorted to sort a stream
// of user defined class objects
import java.util.*;

class Point
{
    Integer x, y;
    Point(Integer x, Integer y) {
        this.x = x;
        this.y = y;
    }

    public String toString() { 
        return this.x + ", "+ this.y;
    } 
}

class GFG
{
    public static void main(String[] args)
    {

        List<Point> aList = new ArrayList<>();
        aList.add(new Point(10, 20));
        aList.add(new Point(5, 10));
        aList.add(new Point(1, 100));
        aList.add(new Point(50, 2000));

        // displaying the stream with elements
        // sorted according to x coordinate
        aList.stream()
        .sorted((p1, p2)->p1.x.compareTo(p2.x))
        .forEach(System.out::println);
    }
}
```

**Output:**

```
1, 100
5, 10
10, 20
50, 2000

```