# Java 中的字符串类 repeat()方法，示例

> 原文:[https://www . geesforgeks . org/string-class-repeat-method-in-Java-with-examples/](https://www.geeksforgeeks.org/string-class-repeat-method-in-java-with-examples/)

这个字符串可以重复 N 次，我们可以生成一个有重复的新字符串。 **repeat()方法**用于返回字符串，该字符串的值是给定字符串重复计数次数的串联。如果字符串为空或计数为零，则返回空字符串。

**语法:**

```
string.repeat(count);
```

**参数:**接受一个整数计数，它是我们想要重复字符串的次数。

**返回:**字符串，其值是给定字符串重复计数次数的串联

**示例:**

```
Input:

string = abc
count = 3

Output:

abcabcabc

Input:

string = xyz
count = 0

Output:

null
```

**算法:**

1.  首先，我们接受字符串的输入。
2.  然后我们使用 repeat()方法来计算我们想要重复的字符串的数量。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the usage of 
// repeat() method

import java.io.*;

class GFG {
    public static void main (String[] args) {

      String string="abc";

      int count=3;

      System.out.println("String :"+string.repeat(count));

      }
}
```

**Output**

```
String :abcabcabc
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the usage of 
// repeat() method

import java.io.*;

class GFG {
    public static void main (String[] args) {

       String string="xyz";
       int count=0;

       System.out.println("string :"+string.repeat(count));

    }
}
```

**Output**

```
string :
```