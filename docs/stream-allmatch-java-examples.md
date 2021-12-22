# Java 中的 Stream allMatch()，示例

> 原文:[https://www . geesforgeks . org/stream-all match-Java-examples/](https://www.geeksforgeeks.org/stream-allmatch-java-examples/)

**Stream allMatch(谓词谓词)**返回该流的所有元素是否与提供的谓词匹配。如果不是确定结果所必需的，它可能不会计算所有元素上的谓词。这是一次 ***短路端子操作。*** 如果终端操作在无限输入时可能在有限时间内终止，则该操作为短路。
**语法:**

```
boolean allMatch(Predicate<**?** super **T**> predicate)

Where, T is the type of the input to the predicate
and the function returns true if either all elements
of the stream match the provided predicate or 
the stream is empty, otherwise false.

```

**注意:**如果流为空，则返回 true，不计算谓词。一旦使用流完成了任何功能，在重新初始化之前就不能再使用它。

**例 1 :** allMatch()函数检查所有元素是否能被 3 整除。

```
// Java code for Stream allMatch
// (Predicate predicate) to check whether 
// all elements of this stream match 
// the provided predicate.
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args) {

    // Creating a list of Integers
    List<Integer> list = Arrays.asList(3, 4, 6, 12, 20);

    // Check if all elements of stream
    // are divisible by 3 or not using 
    // Stream allMatch(Predicate predicate)
    boolean answer = list.stream().allMatch(n-> n % 3 ==0);

    // Displaying the result
    System.out.println(answer);
}
}
```

**输出:**

```
false

```

**示例 2 :** allMatch()函数，检查字符串的长度是否大于 2。

```
// Java code for Stream allMatch
// (Predicate predicate) to check whether 
// all elements of this stream match 
// the provided predicate.
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args) {

    // Creating a Stream of Strings
    Stream<String> stream = Stream.of("Geeks", "for", 
                       "GeeksQuiz", "GeeksforGeeks");

    // Check if all elements of stream
    // have length greater than 2 using
    // Stream allMatch(Predicate predicate)
    boolean answer = stream.allMatch(str -> str.length() > 2);

    // Displaying the result
    System.out.println(answer);
}
}
```

**输出:**

```
true

```

**示例 3 :** allMatch()函数检查所有字符串在第一个索引处是否都有大写字符。

```
// Java code for Stream allMatch
// (Predicate predicate) to check whether 
// all elements of this stream match 
// the provided predicate.
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args) {

    // Creating a Stream of Strings
    Stream<String> stream = Stream.of("Geeks", "for", 
                       "GeeksQuiz", "GeeksforGeeks");

    // Check if Character at 1st index is 
    // UpperCase in all strings or not using
    // Stream allMatch(Predicate predicate)
    boolean answer = stream.allMatch(str-> Character
                       .isUpperCase(str.charAt(1)));

    // Displaying the result
    System.out.println(answer);
}
}
```

**输出:**

```
false

```

**示例 4 :** 使用同一个流完成多个功能

```
// In case we want multiple function to be done.

import java.util.stream.IntStream;

public class MultipleStreamFunction {

    public static void main(String[] args) {

        final String sample = "Om Sarve Bhavantu Sukhinah";

        // converting to Ascii
        IntStream intstreams = sample.chars();

        // All match to check if all Ascii value greater then 100
        boolean answer = intstreams.allMatch(c -> c > 100);
        System.out.println(answer);

        // Need to initialize the stream again
        // to avoid runtime exception
        intstreams = sample.chars();
        // All match to check if all Ascii value greater then 31

        answer = intstreams.allMatch(c -> c > 31);
        System.out.println(answer);

    }
}
```

**输出:**

```
false
true

```