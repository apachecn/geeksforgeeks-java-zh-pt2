# 用 Java 流至数组()，示例

> 原文:[https://www.geeksforgeeks.org/stream-toarray-java-examples/](https://www.geeksforgeeks.org/stream-toarray-java-examples/)

**Stream toArray()** 返回包含该流元素的数组。这是一个 ***终端操作*** ，也就是说，它可能穿越河流产生结果或副作用。执行终端操作后，流管道被认为已消耗，不能再使用。

**语法:**

```
Object[] toArray()

```

**返回值:**函数返回一个包含该流元素的数组。

**例 1 :**

```
// Java code for Stream toArray()
import java.util.*;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a Stream of Integers
        Stream<Integer> stream = Stream.of(5, 6, 7, 8, 9, 10);

        // Using Stream toArray()
        Object[] arr = stream.toArray();

        // Displaying the elements in array arr
        System.out.println(Arrays.toString(arr));
    }
}
```

输出:

```
[5, 6, 7, 8, 9, 10]

```

**例 2 :**

```
// Java code for Stream toArray()
import java.util.*;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a Stream of Strings
        Stream<String> stream = Stream.of("Geeks", "for",
                                          "Geeks", "GeeksQuiz");

        // Using Stream toArray()
        Object[] arr = stream.toArray();

        // Displaying the elements in array arr
        System.out.println(Arrays.toString(arr));
    }
}
```

输出:

```
[Geeks, for, Geeks, GeeksQuiz]

```

**例 3 :**

```
// Java code for Stream toArray()
import java.util.*;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a Stream of Strings
        Stream<String> stream = Stream.of("Geeks", "for",
                                          "gfg", "GeeksQuiz");

        // Using Stream toArray() and filtering
        // the elements that starts with 'G'
        Object[] arr = stream.filter(str
                                     -> str.startsWith("G"))
                           .toArray();

        // Displaying the elements in array arr
        System.out.println(Arrays.toString(arr));
    }
}
```

输出:

```
[Geeks, GeeksQuiz]

```