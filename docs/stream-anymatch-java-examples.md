# Java 中的 Stream anyMatch()，示例

> 原文:[https://www . geesforgeks . org/stream-any match-Java-examples/](https://www.geeksforgeeks.org/stream-anymatch-java-examples/)

**Stream anyMatch(谓词谓词)**返回该流的任何元素是否与提供的谓词匹配。如果不是确定结果所必需的，它可能不会计算所有元素上的谓词。这是一次 ***短路端子操作。*** 如果终端操作在无限输入时可能在有限时间内终止，则该操作为短路。
**语法:**

```
boolean anyMatch(Predicate<**?** super **T**> predicate)

Where, T is the type of the input to the predicate
and the function returns true if any elements of
the stream match the provided predicate, 
otherwise false.

```

**注意:**如果流为空，则返回 false，不计算谓词。
下面给出了一些例子，以便更好地理解函数的实现。

**示例 1 :** anyMatch()函数检查列表中的任何元素是否满足给定条件。

```
// Java code for Stream anyMatch
// (Predicate predicate) to check whether 
// any element of this stream match 
// the provided predicate.
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args) {

    // Creating a list of Integers
    List<Integer> list = Arrays.asList(3, 4, 6, 12, 20);

    // Stream anyMatch(Predicate predicate) 
    boolean answer = list.stream().anyMatch(n
                     -> (n * (n + 1)) / 4 == 5);

    // Displaying the result
    System.out.println(answer);
}
}
```

输出:

```
true

```

**示例 2 :** anyMatch()函数检查列表中的任何元素在第一个索引处是否有大写字母。

```
// Java code for  Stream anyMatch
// (Predicate predicate) to check whether
// any element of this stream match
// the provided predicate.
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a Stream of Strings
        Stream<String> stream = Stream.of("Geeks", "fOr",
                                          "GEEKSQUIZ", "GeeksforGeeks");

        // Check if Character at 1st index is
        // UpperCase in any string or not using
        // Stream anyMatch(Predicate predicate)
        boolean answer = stream.anyMatch(str -> Character.isUpperCase(str.charAt(1)));

        // Displaying the result
        System.out.println(answer);
    }
}
```

输出:

```
true

```