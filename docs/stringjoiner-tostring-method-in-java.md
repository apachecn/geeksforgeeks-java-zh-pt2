# Java 中的 StringJoiner toString()方法

> 原文:[https://www . geesforgeks . org/string joiner-tostring-method-in-Java/](https://www.geeksforgeeks.org/stringjoiner-tostring-method-in-java/)

[StringJoiner](https://www.geeksforgeeks.org/java-util-stringjoiner-java8/) 的 **toString()** 用于将 StringJoiner 转换为 String。它返回当前值，由前缀、到目前为止添加的值(由分隔符分隔)和后缀组成，除非没有添加任何元素，在这种情况下，将返回前缀+后缀或空值字符
**语法:**

```
public String toString()
```

**返回:**该方法返回该字符串的**字符串表示**下面的程序说明了 toString()方法:
**示例 1:** 演示带有分隔符“”的 toString()

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// toString() method of StringJoiner

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
        // using toString() method
        System.out.println("StringJoiner: "
                           + str.toString());
    }
}
```

**Output:** 

```
StringJoiner: Geeks for Geeks
```

**示例 2:** 演示带分隔符“，”的 toString()

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// toString() method of StringJoiner

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
        // using toString() method
        System.out.println("StringJoiner: "
                           + str.toString());
    }
}
```

**Output:** 

```
StringJoiner: Geeks, for, Geeks, A, Computer, Portal
```