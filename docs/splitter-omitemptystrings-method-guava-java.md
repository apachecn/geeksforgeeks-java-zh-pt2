# Splitter omittemptystrings()方法|番石榴| Java

> 原文:[https://www . geesforgeks . org/splitter-omittemptystrings-method-guava-Java/](https://www.geeksforgeeks.org/splitter-omitemptystrings-method-guava-java/)

方法**OmittemptyStrings()**返回一个行为与此拆分器相同的拆分器，但会自动从结果中省略空字符串。例如，Splitter.on('，')。omitEmptyStrings()。split(“、a、、、、b、c、”)返回一个只包含[“a”、“b”、“c”]的 iterable。

**语法:**

```
public Splitter omitEmptyStrings()

```

**返回值:**该方法返回具有所需配置的拆分器。

> **注意:**如果在创建拆分器时还指定了任一 trimResults 选项，则该拆分器总是在检查是否为空之前先修剪结果。例如，
> 
> **Splitter.on(':')。omitEmptyStrings()。trimResults()。拆分(":::)**
> 
> 返回一个空的 iterable。

以下示例说明了 omitEmptyStrings()方法的工作原理:

**例 1:**

```
// Java code to show implementation of
// omitEmptyStrings() method
// of Guava's Splitter Class

import com.google.common.base.Splitter;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a string variable
        String str = "geeks,,  for,,,  geeks,, noida,,, classes";
        System.out.println("String with empty strings: \n"
                           + str);

        // Using omitEmptyStrings() method.
        // Two delimiters sometimes occur right next
        // to each other. This means an empty entry.
        // But often in splitting, we don't want
        // to keep empty entries.
        List<String> myList = Splitter.on(', ').
         trimResults().omitEmptyStrings().splitToList(str);

        System.out.println("\nString with empty"
                           + " strings removed: \n"
                           + myList);
    }
}
```

**Output:**

```
String with empty strings: 
geeks,,  for,,,  geeks,, noida,,, classes

String with empty strings removed: 
[geeks, for, geeks, noida, classes]

```

**例 2:**

```
// Java code to show implementation of
// omitEmptyStrings() method
// of Guava's Splitter Class

import com.google.common.base.Splitter;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a string variable
        String str = "Hello..$.$ everyone..{content}amp; $ what's up..?";
        System.out.println("String with empty strings: \n"
                           + str);

        // Using omitEmptyStrings() method.
        // Two delimiters sometimes occur right next
        // to each other. This means an empty entry.
        // But often in splitting, we don't want
        // to keep empty entries.
        List<String> myList = Splitter.on('.').
            trimResults().omitEmptyStrings().splitToList(str);

        System.out.println("\nString with empty"
                           + " strings removed: \n"
                           + myList);
    }
}
```

**Output:**

```
String with empty strings: 
Hello..$.$ everyone..{content}amp; $ what's up..?

String with empty strings removed: 
[Hello, $, $ everyone, {content}amp; $ what's up, ?]

```