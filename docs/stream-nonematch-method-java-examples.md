# 流非匹配()方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/stream-non match-method-Java-examples/](https://www.geeksforgeeks.org/stream-nonematch-method-java-examples/)

一个 ***流是一个支持各种方法*** 的对象序列，这些方法可以被流水线化以产生期望的结果。Stream 类的 **noneMatch()** 返回该流中是否没有元素与提供的谓词匹配。如果不是确定结果所必需的，它可能不会计算所有元素上的谓词。这是 ***短路端子操作。*** 如果当出现无限输入时，终端操作可能在有限时间内终止，则该操作为短路。

> **提示:**有效。 ***对面流 anymatch()方法*** 。

**语法:**

```
boolean noneMatch(Predicate<? super T> predicate)
```

其中，T 是谓词的输入类型，如果流中没有元素与提供的谓词匹配，或者流为空，则函数返回 true，否则返回 false。

> **注意:**如果流为空，则返回 true，不计算谓词。**T3】**

现在我们将讨论几个例子，在这些例子中，我们将覆盖不同的场景，同时通过干净的 java 程序实现 Stream noneMatch()方法，如下所示:

*   检查是否没有特定自定义长度的字符串
*   检查是否有小于 0 的元素
*   检查在需要的位置没有需要字符的元素

**例 1:** 检查是否没有长度为 4 的字符串。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate noneMatch() method
// of Stream class to check whether
// no elements of this stream match the
// provided predicate (Predicate predicate)

// Importing Stream class from java.util.stream sub package
import java.util.stream.Stream;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating a Stream of strings
        // Custom input strings are passed as arguments
        Stream<String> stream
            = Stream.of("CSE", "C++", "Java", "DS");

        // Now using Stream noneMatch(Predicate predicate)
        // and later storing the boolean answer as
        boolean answer
            = stream.noneMatch(str -> (str.length() == 4));

        // Printing the boolean value on the console
        System.out.println(answer);
    }
}
```

**Output**

```
false
```

**例 2 :** 检查没有小于 0 的元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate noneMatch() method
// of Stream class to check whether no elements
// of this stream match the provided predicate

// Importing required utility classes
import java.util.*;

// Main class
class GFG {

    // amin driver method
    public static void main(String[] args)
    {
        // Creating a list of Integers using asList() of
        // Arrays class by declaring object of List
        List<Integer> list = Arrays.asList(4, 0, 6, 2);

        // Using Stream noneMatch(Predicate predicate) and
        // storing the boolean value
        boolean answer
            = list.stream().noneMatch(num -> num < 0);

        // Printing and displaying the above boolean value
        System.out.println(answer);
    }
}
```

**Output**

```
true
```

**例 3 :** 检查所需位置是否没有需要字符的元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate noneMatch() method
// of Stream class to check whether no elements of
// this stream match the provided predicate

// Importing required classes
import java.util.stream.Stream;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a Stream of Strings using of() method
        // by creating object of Stream of string type
        Stream<String> stream
            = Stream.of("Geeks", "fOr", "GEEKSQUIZ",
                        "GeeksforGeeks", "CSe");

        // Using Stream noneMatch(Predicate predicate)
        // and storing the boolean value
        boolean answer = stream.noneMatch(
            str
            -> Character.isUpperCase(str.charAt(1))
                   && Character.isLowerCase(str.charAt(2))
                   && str.charAt(0) == 'f');

        // Printing the above boolean value on console
        System.out.println(answer);
    }
}
```

**Output**

```
false
```