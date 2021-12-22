# Java 中的 StringBuffer appendCodePoint()方法，带示例

> 原文:[https://www . geesforgeks . org/stringbuffer-appendcodepoint-method-in-Java/](https://www.geeksforgeeks.org/stringbuffer-appendcodepoint-method-in-java/)

***StringBuffer 类的 appendCodePoint()方法*** 将 CodePoint 参数的字符串表示追加到这个序列中，对于这个序列，我们需要具备 [ASCII 表](https://www.geeksforgeeks.org/ascii-table/)的先决知识，因为只有这样，我们才能够感知输出为什么要追加特定的文字，因为已经分配了一个整数值。

```java
--> appendCodePoint() Method
    --> StringBuffer Class
        --> java.lang Package 
```

**语法:**

```java
public StringBuffer appendCodePoint(*int cp*)
```

**参数:**该方法接受整数类型的单个参数 *cp* ，并引用 Unicode 代码点。

**返回类型:**方法在追加由代码点表示的字符串后返回该对象。

**插图:**

```java
Input : StringBuffer = Apple
        int cp = 65
Output: AppleA 
```

```java
Input : StringBuffer = GeeksforGeeks
       int cp = 156
Output: GeeksforGeeks?
```

**解释:**因为 65 是“A”的 ASCII 值，156 是“？”的 ASCII 值

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate appendCodePoint() Method
// of StringBuffer class

// Importing required classes
import java.lang.*;

// Main class
public class GFG {

    // Main drive method
    public static void main(String[] args)
    {

        // Reading passed string
        StringBuffer sbf
            = new StringBuffer("Geeksforgeeks");

        // Printing the string
        System.out.println("String buffer = " + sbf);

        // Appending the CodePoint as String to the string
        // buffer
        sbf.appendCodePoint(65);

        // Printing the string again after
        // appending codePoint as string
        System.out.println("After appending CodePoint is = "
                           + sbf);
    }
}
```

**Output:** 

```java
String buffer = Geeksforgeeks
After appending CodePoint is = GeeksforgeeksA
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate appendCodePoint() Method
// of StringBuffer class

// Importing required classes
import java.lang.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args) {

        // Reading passed string by creating objecgt of class
        StringBuffer sbf
            = new StringBuffer("Geeksforgeeks");

        System.out.println("String buffer = " + sbf);

        // Here it appends the CodePoint as
        // string to the string buffer
        sbf.appendCodePoint(54);

        System.out.println("After appending CodePoint is = "
                           + sbf);
    }
}
```

**Output:** 

```java
String buffer = Geeksforgeeks
After appending CodePoint is = Geeksforgeeks6
```

**例 3:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate appendCodePoint() Method
// of StringBuffer class

// Importing required classes
import java.lang.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Reading passed string
        StringBuffer sbf
            = new StringBuffer("Geeksforgeeks");

        // Printing string on console
        System.out.println("String buffer = " + sbf);

        // Appending the codePoint as string
        // to the string buffer
        sbf.appendCodePoint(43);

        // Printing the string on console after
        // appending codepoint as string
        System.out.println("After appending CodePoint is = "
                           + sbf);
    }
}
```

**Output:** 

```java
String buffer = Geeksforgeeks
After appending CodePoint is = Geeksforgeeks+
```