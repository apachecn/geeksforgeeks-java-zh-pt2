# Java 中的 Stream.distinct()

> 原文:[https://www.geeksforgeeks.org/stream-distinct-java/](https://www.geeksforgeeks.org/stream-distinct-java/)

**distinct()** 返回由流中不同元素组成的流。distinct()是**流**界面的方法。该方法使用 *hashCode()* 和 *equals()* 方法获取不同的元素。在有序流的情况下，不同元素的选择是稳定的。但是，在无序流的情况下，不同元素的选择不一定是稳定的，可能会发生变化。distinct()执行**有状态中间操作**，即它在内部保持某种状态来完成操作。

**语法:**

```
Stream<T> distinct()

Where, Stream is an interface and the function
returns a stream consisting of the distinct 
elements.

```

下面给出了一些例子，以便更好地理解函数的实现。
**例 1 :**

```
// Implementation of Stream.distinct()
// to get the distinct elements in the List
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a list of integers
        List<Integer> list = Arrays.asList(1, 1, 2, 3, 3, 4, 5, 5);

        System.out.println("The distinct elements are :");

        // Displaying the distinct elements in the list
        // using Stream.distinct() method
        list.stream().distinct().forEach(System.out::println);
    }
}
```

输出:

```
The distinct elements are :
1
2
3
4
5

```

**例 2 :**

```
// Implementation of Stream.distinct()
// to get the distinct elements in the List
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a list of strings
        List<String> list = Arrays.asList("Geeks", "for", "Geeks",
                                          "GeeksQuiz", "for", "GeeksforGeeks");

        System.out.println("The distinct elements are :");

        // Displaying the distinct elements in the list
        // using Stream.distinct() method
        list.stream().distinct().forEach(System.out::println);
    }
}
```

输出:

```
The distinct elements are :
Geeks
for
GeeksQuiz
GeeksforGeeks

```

**例 3 :**

```
// Implementation of Stream.distinct()
// to get the count of distinct elements
// in the List
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a list of strings
        List<String> list = Arrays.asList("Geeks", "for", "Geeks",
                                          "GeeksQuiz", "for", "GeeksforGeeks");

        // Storing the count of distinct elements
        // in the list using Stream.distinct() method
        long Count = list.stream().distinct().count();

        // Displaying the count of distinct elements
        System.out.println("The count of distinct elements is : " + Count);
    }
}
```

输出:

```
The count of distinct elements is : 4

```