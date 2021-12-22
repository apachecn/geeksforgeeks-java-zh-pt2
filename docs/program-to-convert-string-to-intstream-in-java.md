# 用 Java 将字符串转换成 IntStream 的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-string-to-int stream-in-Java/](https://www.geeksforgeeks.org/program-to-convert-string-to-intstream-in-java/)

给定一个字符串，任务是将这个字符串转换成一个包含字符的 ASCII 值作为元素的输入流。

**例:**

```
Input: String = Geeks
Output: 71, 101, 101, 107, 115

Input: String = GeeksForGeeks
Output: 71, 101, 101, 107, 115, 70, 111, 114, 71, 101, 101, 107, 115

```

**算法:**

1.  Gets the string to be converted.
2.  Use the chars () method to convert it to IntStream.
3.  Printed IntStream.

以下是上述方法的实现:

```
// Java program to convert
// String to IntStream

import java.util.stream.IntStream;

class GFG {
    public static void main(String[] args)
    {

        // Get the String to be converted
        String string = "Geeks";

        // Print the String
        System.out.println("String: " + string);

        // Convert String to IntStream using chars() method
        IntStream intStream = string.chars();

        // Print the elements of the IntStream
        intStream.forEach(System.out::println);
    }
}
```

**输出:**

```
String: Geeks
71
101
101
107
115

```