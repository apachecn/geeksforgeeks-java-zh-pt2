# Java 中 StringBuffer 反向()方法，带示例

> 原文:[https://www . geesforgeks . org/stringbuffer-reverse-in-method-in-Java/](https://www.geeksforgeeks.org/stringbuffer-reverse-method-in-java/)

Java.lang.StringBuffer.reverse()是一个内置方法，用于反转 StringBuffer 中的字符。方法使该字符序列被序列的反码替换。
**语法:**

```java
public StringBuffer reverse()
```

**参数:**该方法不取任何参数。
**返回值:**该方法在反转字符后返回 StringBuffer。
**示例:**

```java
Input: StringBuffer = GeeksforGeeks
Output = !skeegrofskeeG

Input: StringBuffer = Hello World
Output = !dlroW olleH
```

下面的程序说明了 java.lang.StringBuffer.reverse()方法:
**程序 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// java.lang.StringBuffer.reverse()
import java.lang.*;

public class Test {

    public static void main(String args[])
    {
        StringBuffer sbf = new StringBuffer("Geeksforgeeks!");
        System.out.println("String buffer = " + sbf);

        // Here it reverses the string buffer
        sbf.reverse();
        System.out.println("String buffer after reversing = " + sbf);
    }
}
```

**Output:** 

```java
String buffer = Geeksforgeeks!
String buffer after reversing = !skeegrofskeeG
```

**程序 2:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// java.lang.StringBuffer.reverse()
import java.lang.*;

public class Test {

    public static void main(String args[])
    {
        StringBuffer sbf = new StringBuffer("1 2 3 4 5 6 7 8 9 10");
        System.out.println("String buffer  = " + sbf);

        // Here it reverses the string buffer
        sbf.reverse();
        System.out.println("String buffer after reversing = " + sbf);
    }
}
```

**Output:** 

```java
String buffer  = 1 2 3 4 5 6 7 8 9 10
String buffer after reversing = 01 9 8 7 6 5 4 3 2 1
```