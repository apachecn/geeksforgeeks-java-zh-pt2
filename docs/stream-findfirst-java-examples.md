# Java 中的 Stream findFirst()示例

> 原文:[https://www . geesforgeks . org/stream-find first-Java-examples/](https://www.geeksforgeeks.org/stream-findfirst-java-examples/)

**Stream findFirst()** 返回一个描述该流的**第一个**元素的可选值(一个可以包含也可以不包含非空值的容器对象)，如果该流为空，则返回一个空的可选值。如果流没有相遇顺序，那么可以返回任何元素。

**语法:**

```
Optional<**T**> findFirst()

Where, Optional is a container object which
may or may not contain a non-null value 
and T is the type of objects and the function
returns an Optional describing the first element 
of this stream, or an empty Optional if the stream is empty.

```

**异常:**如果选择的元素为空，则抛出 ***空指针异常*** 。

**注意:** findAny()是一个 ***端子-短路*** 操作的 Stream 界面。此方法返回满足中间操作的第一个元素。

**示例 1 :** 整数流上的 findFirst()函数。

```
// Java code for Stream findFirst()
// which returns an Optional describing
// the first element of this stream, or
// an empty Optional if the stream is empty.
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a List of Integers
        List<Integer> list = Arrays.asList(3, 5, 7, 9, 11);

        // Using Stream findFirst()
        Optional<Integer> answer = list.stream().findFirst();

        // if the stream is empty, an empty
        // Optional is returned.
        if (answer.isPresent()) {
            System.out.println(answer.get());
        }
        else {
            System.out.println("no value");
        }
    }
}
```

输出:

```
3

```

**示例 2 :** 字符串流上的 findFirst()函数。

```
// Java code for Stream findFirst()
// which returns an Optional describing
// the first element of this stream, or
// an empty Optional if the stream is empty.
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a List of Strings
        List<String> list = Arrays.asList("GeeksforGeeks", "for",
                                          "GeeksQuiz", "GFG");

        // Using Stream findFirst()
        Optional<String> answer = list.stream().findFirst();

        // if the stream is empty, an empty
        // Optional is returned.
        if (answer.isPresent()) {
            System.out.println(answer.get());
        }
        else {
            System.out.println("no value");
        }
    }
}
```

输出:

```
GeeksforGeeks

```