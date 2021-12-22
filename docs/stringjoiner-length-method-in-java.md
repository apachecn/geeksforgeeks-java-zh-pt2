# Java 中 StringJoiner length()方法

> 原文:[https://www . geesforgeks . org/stringjoiner-length-method-in-Java/](https://www.geeksforgeeks.org/stringjoiner-length-method-in-java/)

[字符串连接符](https://www.geeksforgeeks.org/java-util-stringjoiner-java8/)的**长度()**用于找出字符中字符串连接符的长度。它返回该字符串连接器的字符串表示形式的长度。请注意，如果没有调用任何 add 方法，那么将返回字符串表示的长度(前缀+后缀或空值)。该值应等效于 toString()。长度()。
**语法:**

```java
public int length()
```

**返回:**此方法返回 StringJoiner 当前值的**长度**
下面的程序说明了 length()方法:
**示例 1:** 演示带分隔符“”的 length()

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// length() method of StringJoiner

import java.util.StringJoiner;

public class GFG {
    public static void main(String[] args)
    {

        // Creating StringJoiner with delimiter " "
        StringJoiner str = new StringJoiner(" ");

        // Adding elements in the StringJoiner
        str.add("Geeks");
        str.add("for");
        str.add("Geeks");

        // Print the StringJoiner
        System.out.println("StringJoiner: "
                           + str.toString());

        // Printing the length of str
        // using length() method
        System.out.println(str.length());
    }
}
```

**Output:** 

```java
StringJoiner: Geeks for Geeks
15
```

**示例 2:** 用分隔符“，”演示长度()

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// length() method of StringJoiner

import java.util.StringJoiner;

public class GFG {
    public static void main(String[] args)
    {

        // Creating StringJoiner with delimiter ""
        StringJoiner str = new StringJoiner(", ");

        // Adding elements in the StringJoiner
        str.add("Geeks");
        str.add("for");
        str.add("Geeks");
        str.add("A");
        str.add("Computer");
        str.add("Portal");

        // Print the StringJoiner
        System.out.println("StringJoiner: "
                           + str.toString());

        // Printing the length of str
        // using length() method
        System.out.println(str.length());
    }
}
```

**Output:** 

```java
StringJoiner: Geeks, for, Geeks, A, Computer, Portal
38
```