# 用 Java 将 IntStream 转换为 String 的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-int stream-to-string-in-Java/](https://www.geeksforgeeks.org/program-to-convert-intstream-to-string-in-java/)

给定一个包含 ASCII 值的输入流，任务是将该输入流转换为包含与 ASCII 值对应的字符的字符串。

**示例:**

```java
Input: IntStream = 71, 101, 101, 107, 115
Output: Geeks

Input: IntStream = 71, 101, 101, 107, 115, 70, 111, 114, 71, 101, 101, 107, 115
Output: GeeksForGeeks

```

**算法:**

1.  获取要转换的输入流。
2.  借助字符串生成器将输入流转换为字符串
3.  收集形成的字符串生成器
4.  使用 to String()方法将字符串生成器转换为字符串。
5.  打印形成的字符串。

下面是上述方法的实现:

```java
// Java program to convert
// String to IntStream

import java.util.stream.IntStream;

class GFG {
    public static void main(String[] args)
    {

        // Get the String to be converted
        IntStream intStream = "Geeks".chars();

        // Convert IntStream to String
        String string = intStream
                            .collect(StringBuilder::new,
                                     StringBuilder::appendCodePoint,
                                     StringBuilder::append)
                            .toString();

        // Print the String
        System.out.println("String: " + string);
    }
}
```

**输出:**

```java
String: Geeks

```