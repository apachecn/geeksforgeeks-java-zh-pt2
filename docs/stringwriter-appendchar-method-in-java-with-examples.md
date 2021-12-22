# Java 中 StringWriter 追加(char)方法示例

> 原文:[https://www . geesforgeks . org/stringwriter-append char-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringwriter-appendchar-method-in-java-with-examples/)

Java 中 **[StringWriter](https://www.geeksforgeeks.org/java-io-stringwriter-class-in-java/)** 类的**追加(char)** 方法用于在编写器上追加指定的 char 值。这个字符值被作为一个参数。

**语法:**

```java
public void append(char charValue)
```

**参数:**该方法接受一个强制参数**字符值**，它是要附加到编写器上的字符值。

**返回值:**此方法不返回值。

下面的程序说明了 append(char)方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// StringWriter append(char) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a StringWriter instance
            StringWriter writer
                = new StringWriter();

            // Append the char value 'A'
            // to this writer using append() method
            // This will put the charValue in the
            // writer till it is appended on the console
            writer.append('A');

            System.out.println(writer.toString());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
A

```

**程序 2:**

```java
// Java program to demonstrate
// StringWriter append(char) method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a StringWriter instance
            StringWriter writer
                = new StringWriter();

            // Append the char value 'G'
            // to this writer using append() method
            // This will put the charValue in the
            // writer till it is appended on the console
            writer.append('G');

            System.out.println(writer.toString());
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