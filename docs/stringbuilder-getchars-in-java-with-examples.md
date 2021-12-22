# Java 中的 StringBuilder getChars()示例

> 原文:[https://www . geeksforgeeks . org/stringbuilder-getchars-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuilder-getchars-in-java-with-examples/)

StringBuilder 类**的 **getChars(int srcBegin，int srcEnd，char[] dst，int dstegin)**方法将 StringBuilder 包含的字符串中从给定索引:srcBegin 到 index:srcEnd-1 的字符复制到作为参数传递给函数的 char 数组中。**

*   字符从 StringBuilder 复制到数组 dst[]中，从索引:dstBegin 开始，到索引:dst begin+(srcEnd-srcBegin)–1 结束。
*   要从 StringBuilder 复制到数组的第一个字符位于索引 srcBegin，最后一个要复制的字符位于索引 srcEnd-1。
*   要复制的字符总数等于 srcEnd-srcBegin。

**语法:**

```java
public void getChars(int srcBegin, int srcEnd, 
                          char[] dst, int dstBegin)
```

**参数:**该方法接受四个不同的参数:

*   **srcBegin:** 代表我们必须开始复制的索引。
*   **srcEnd:** 代表我们必须停止复制的索引。
*   **dst:** 表示要将数据复制到的数组。
*   **dstBegin:** 代表我们开始粘贴复制数据的目的数组的索引。

**返回值:**这个方法不返回任何东西。

**异常:**此方法抛出**StringIndexOutOfBoundsException**如果:

*   srcBegin < 0
*   dstBegin < 0
*   srcBegin > srcEnd
*   srcEnd > this.length()
*   dstbegin+src end-src begin > dst . length

以下程序演示了 StringBuilder 类的 getChars()方法:

**例 1:**

```java
// Java program to demonstrate
// the getChars() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder
            str
            = new StringBuilder("WelcomeGeeks");

        // print string
        System.out.println("String = "
                           + str.toString());

        // create a char Array
        char[] array = new char[7];

        // get char from index 0 to 7
        // and store in array start index 0
        str.getChars(0, 7, array, 0);

        // print char array after operation
        System.out.print("Char array contains : ");

        for (int i = 0; i < array.length; i++) {
            System.out.print(array[i] + " ");
        }
    }
}
```

**Output:**

```java
String = WelcomeGeeks
Char array contains : W e l c o m e

```

**例 2:**

```java
// Java program to demonstrate
// the getChars() Method.

import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder
            str
            = new StringBuilder("evil dead_01");

        // print string
        System.out.println("String = "
                           + str.toString());

        // create a char Array
        char[] array = new char[10];

        // initialize all character to _(underscore).
        Arrays.fill(array, '_');

        // get char from index 5 to 9
        // and store in array start index 3
        str.getChars(5, 9, array, 3);

        // print char array after operation
        System.out.print("char array contains : ");

        for (int i = 0; i < array.length; i++) {
            System.out.print(array[i] + " ");
        }
    }
}
```

**Output:**

```java
String = evil dead_01
char array contains : _ _ _ d e a d _ _ _

```

**示例 3:** 演示 StringIndexOutOfBoundException

```java
// Java program to demonstrate
// exception thrown by the getChars() Method.

import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder
            str
            = new StringBuilder("evil dead_01");

        // create a char Array
        char[] array = new char[10];

        // initialize all character to _(underscore).
        Arrays.fill(array, '_');

        try {

            // if start is greater then end
            str.getChars(5, 2, array, 0);
        }

        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
Exception: java.lang.StringIndexOutOfBoundsException: srcBegin > srcEnd

```

**参考:**
[https://docs . Oracle . com/javae/10/docs/API/Java/lang/string builder . html # get hars(int，int，char%5B%5D，int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuilder.html#getChars(int, int, char%5B%5D, int))