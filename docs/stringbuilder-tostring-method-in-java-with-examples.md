# Java 中的 StringBuilder toString()方法，带示例

> 原文:[https://www . geeksforgeeks . org/stringbuilder-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuilder-tostring-method-in-java-with-examples/)

[字符串生成器类](https://www.geeksforgeeks.org/stringbuilder-class-in-java-with-examples/)的 **toString()** 方法是用于返回表示字符串生成器对象所包含数据的字符串的内置方法。创建并初始化一个新的字符串对象，以从该字符串生成器对象中获取字符序列，然后由 toString()返回字符串。对象包含的对该序列的后续更改不会影响字符串的内容。

**语法:**

```
public abstract String toString() ;
```

**返回值:**这个方法总是返回一个代表 StringBuilder 对象包含的数据的字符串。

因为这是一个非常基本的方法，所以我们将在干净的 java 程序中讨论它，以了解它的工作原理。在类内部，它的定义如下，这将使您更好地理解它的实际工作原理。

```
return getClass().getName()+ "@" + Integer.toHexString(hashCode);
```

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate toString() Method

// Importing I/O classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
            = new StringBuilder("GeeksForGeeks");

        // Print and display the string
        // using standard toString() method
        System.out.println("String contains = "
                           + str.toString());
    }
}
```

**Output**

```
String contains = GeeksForGeeks
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate toString() Method.

// Importing input output classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a StringBuilder object with
        // a String pass as parameter
        StringBuilder str = new StringBuilder(
            "Geeks for Geeks contribute");

        // Print and display the string
        // using to.String() method
        System.out.println("String contains = "
                           + str.toString());
    }
}
```

**Output**

```
String contains = Geeks for Geeks contribute
```

现在我们已经讨论完了基本示例，让我们通过使用 to 将字符串数组转换为单个字符串来对其进行操作。String()方法。在这里，我们将创建一个 StringBuilder 类对象，然后将字符串数组存储为它的对象。稍后，我们将创建另一个字符串，并将在其中抛出所有元素。最后，我们将打印这个字符串。

**例 3:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Convert Array of Strings to A String
// Using toString() method

// Importing required classes
import java.io.*;
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Random array of string as input
        String gfg[] = { "Are", "You", "A", "Programmer" };

        // Creating object of StringBuilder class
        StringBuilder obj = new StringBuilder();

        // Adding above arrays of strings to
        // Stringbuilder object
        obj.append(gfg[0]);
        obj.append(" " + gfg[1]);
        obj.append(" " + gfg[2]);
        obj.append(" " + gfg[3]);

        // Note if elements are more then
        // we will be using loops to append(add)

        // Creating a single string
        String str = obj.toString();

        // Print and display the above string
        // containing all strings as a single string
        // using toString() method
        System.out.println(
            "Single string generated using toString() method is --> "
            + str);
    }
}
```

**Output**

```
Single string generated using toString() method is --> Are You A Programmer
```