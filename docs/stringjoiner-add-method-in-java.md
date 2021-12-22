# Java 中 StringJoiner add()方法

> 原文:[https://www . geesforgeks . org/string joiner-add-method-in-Java/](https://www.geeksforgeeks.org/stringjoiner-add-method-in-java/)

[字符串连接符](https://www.geeksforgeeks.org/java-util-stringjoiner-java8/)的**add(CharSequence new element)**添加给定的 CharSequence 值的副本作为字符串连接符值的下一个元素。如果新元素为空，则添加“空”。
**语法:**

```
public StringJoiner add(CharSequence newElement)
```

**参数:**该方法取一个强制参数 **newElement** ，即需要添加的元素。
**返回:**此方法返回对此字符串的引用下面的程序说明了 add()方法:
**示例 1:** 演示用分隔符“”添加()

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// add() method of StringJoiner

import java.util.StringJoiner;

public class GFG1 {
    public static void main(String[] args)
    {

        // Creating StringJoiner with delimiter " "
        StringJoiner str = new StringJoiner(" ");

        // Adding elements in the StringJoiner
        str.add("Geeks");
        str.add("for");
        str.add("Geeks");

        // Print the StringJoiner
        System.out.println(str.toString());
    }
}
```

**Output:** 

```
Geeks for Geeks
```

**示例 2:** 演示使用分隔符“，”添加()

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// add() method of StringJoiner

import java.util.StringJoiner;

public class GFG1 {
    public static void main(String[] args)
    {

        // Creating StringJoiner with delimiter ","
        StringJoiner str = new StringJoiner(",");

        // Adding elements in the StringJoiner
        str.add("Geeks");
        str.add("for");
        str.add("Geeks");

        // Print the StringJoiner
        System.out.println(str.toString());
    }
}
```

**Output:** 

```
Geeks,for,Geeks
```