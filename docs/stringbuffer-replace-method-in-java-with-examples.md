# StringBuffer 用示例替换 Java 中的()方法

> 原文:[https://www . geesforgeks . org/stringbuffer-用示例替换 java 中的方法/](https://www.geeksforgeeks.org/stringbuffer-replace-method-in-java-with-examples/)

StringBuffer.replace()是一种内置方法，用于将该序列的子字符串中的字符替换为指定字符串中的字符。这里简单地删除子串中的字符，并在开始处插入其他字符。
**语法:**

```java
public StringBuffer replace(*int first, int last, String st*)
```

**参数:**该方法接受三个参数。

*   *第一个*:这是整数类型，指的是起始索引。
*   *最后*:这是整数类型，指的是结束索引。
*   *st* :这是字符串类型，指的是将替换先前内容的字符串。

**返回值:**该方法在执行上述操作后返回该对象。
**异常:**如果*第一个*为负，大于长度()，或大于*最后一个*，则*StringIndexOutOfBoundsException*。
**示例:**

```java
Input:
StringBuffer= "The first planet of solar system is merrhxy"
first = 39
last = 42
st = "cur"

Output: The first planet of solar system is mercury
```

下面的程序说明了 java.lang.StringBuffer.replace()方法:
**程序 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// java.lang.StringBuffer.replace()

import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        StringBuffer sbf = new StringBuffer("Welcome to Geekshssgeeks");
        System.out.println("string buffer = " + sbf);

        // Replacing substring from index 15 to index 18
        sbf.replace(15, 18, "for");

        System.out.println("After replacing string buffer= " + sbf);
    }
}
```

**Output:** 

```java
string buffer = Welcome to Geekshssgeeks
After replacing string buffer= Welcome to Geekforsgeeks
```

**程序 2:** 通过负指数时:

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// java.lang.StringBuffer.replace()

import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        StringBuffer sbf = new StringBuffer("Welcome to Geekshssgeeks");
        System.out.println("string buffer = " + sbf);

        // Replacing substring from index -15 to index -18
        sbf.replace(-15, -18, "for");

        System.out.println("After replacing string buffer= " + sbf);
    }
}
```

**Output:** 

```java
Exception in thread "main" java.lang.StringIndexOutOfBoundsException: 
String index out of range: -15
at java.lang.AbstractStringBuilder.replace(AbstractStringBuilder.java:851)
at java.lang.StringBuffer.replace(StringBuffer.java:452)
at Geeks.main(Geeks.java:14)
```

**程序 3:** 当通过的索引大于长度时

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to illustrate the
// java.lang.StringBuffer.replace()

import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        StringBuffer sbf = new StringBuffer("Welcome to Geekshssgeeks");
        System.out.println("string buffer = " + sbf);

        // Replacing substring from index 215 to index 218
        sbf.replace(215, 218, "for");

        System.out.println("After replacing string buffer= " + sbf);
    }
}
```

**Output:** 

```java
Exception in thread "main" java.lang.StringIndexOutOfBoundsException: 
start > length()
at java.lang.AbstractStringBuilder.replace(AbstractStringBuilder.java:853)
at java.lang.StringBuffer.replace(StringBuffer.java:452)
at Geeks.main(Geeks.java:14)
```