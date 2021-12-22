# PrintWriter 用示例在 Java 中追加(CharSequence，int，int)方法

> 原文:[https://www . geesforgeks . org/print writer-appendcharsequence-int-int-method-in-Java-with-examples/](https://www.geeksforgeeks.org/printwriter-appendcharsequence-int-int-method-in-java-with-examples/)

Java 中类的**追加(charSequence，int，int)** 方法用于在流中追加指定 CharSequence 的指定部分。这个字符序列作为一个参数。要写入的起始索引和结束索引也作为参数。

**语法:**

> public see append(charsequence charsequence，int startingIndex，int endingindex)

**参数:**该方法接受三个强制参数:

*   **字符序列**是要写入流中的字符序列。
*   **起始索引**是字符部分的起始索引。
*   **endingIndex** 是要写入流的结束索引。

**返回值:**此方法不返回值。

下面的方法说明了 append(CharSequence，int，int)方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// PrintWriter append(CharSequence, int, int) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // Get the charSequence
            // to be written in the stream
            CharSequence charSequence = "GeeksForGeeks";

            // Get the starting index
            int startingIndex = 0;

            // Get the length of char
            int endingIndex = 5;

            // Write the portion of the charSequence
            // to this writer using append() method
            // This will put the charSequence in the stream
            // till it is printed on the console
            writer.append(charSequence,
                          startingIndex,
                          endingIndex);

            writer.flush();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
Geeks

```

**程序 2:**

```java
// Java program to demonstrate
// PrintWriter append(CharSequence, int, int) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a PrintWriter instance
            PrintWriter writer
                = new PrintWriter(System.out);

            // Get the charSequence
            // to be written in the stream
            CharSequence charSequence = "GFG";

            // Get the starting index
            int startingIndex = 2;

            // Get the length of char
            int endingIndex = 3;

            // Write the portion of the charSequence
            // to this writer using append() method
            // This will put the charSequence in the stream
            // till it is printed on the console
            writer.append(charSequence,
                          startingIndex,
                          endingIndex);

            writer.flush();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
G

```