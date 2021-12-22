# Java 中 StringBuffer getChars()方法，带示例

> 原文:[https://www . geeksforgeeks . org/stringbuffer-getchars-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuffer-getchars-method-in-java-with-examples/)

**StringBuffer 类**的 **getChars(int srcBegin，int srcEnd，char【】dst，int dstegin)**方法将从索引:srcBegin 到索引:srcEnd-1 开始的字符从实际序列复制到作为参数传递给函数的 char 数组中。

*   字符被复制到 char dst[]数组中，开始于索引:dstBegin，结束于索引:dst begin+(SRcend-SRcbegin)–1。
*   要复制到数组的第一个字符位于索引 srcBegin，最后一个字符位于索引 srcEnd-1。
*   要复制的字符总数等于 srcEnd-srcBegin。

**语法:**

```
public void getChars(int srcBegin, int srcEnd, 
                          char[] dst, int dstBegin)
```

**参数:**该方法取四个参数:

*   **srcBegin** : int 值代表开始复制的索引。
*   **srcEnd** : int 值代表要停止复制的索引。
*   **dst**:char 的数组表示要将数据复制到的数组。
*   **dstBegin** : int 值代表开始粘贴复制数据的目的数组的索引。

**返回:**此方法不返回任何内容。

**异常:**如果出现以下情况，此方法将引发 StringIndexOutOfBoundsException:

*   srcBegin < 0
*   dstBegin < 0
*   srcBegin > srcEnd
*   srcEnd > this.length()
*   dstbegin+src end-src begin > dst . length

以下程序演示了 StringBuffer 类的 getChars()方法:

**例 1:**

```
// Java program to demonstrate
// the getChars() Method.

import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer
            str
            = new StringBuffer("Geeks For Geeks");

        // print string
        System.out.println("String = "
                           + str.toString());

        // create a char Array
        char[] array = new char[15];

        // initialize all character to .(dot).
        Arrays.fill(array, '.');

        // get char from index 0 to 9
        // and store in array start index 3
        str.getChars(0, 9, array, 1);

        // print char array after operation
        System.out.print("char array contains : ");

        for (int i = 0; i < array.length; i++) {
            System.out.print(array[i] + " ");
        }
    }
}
```

**Output:**

```
String = Geeks For Geeks
char array contains : . G e e k s   F o r . . . . .

```

**示例 2:** 演示 StringIndexOutOfBoundsException。

```
// Java program to demonstrate
// exception thrown by the getChars() Method.

import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer
            str
            = new StringBuffer("Contribute Geeks");

        // create a char Array
        char[] array = new char[10];

        // initialize all character to $(dollar sign).
        Arrays.fill(array, '{content}apos;);

        try {

            // if start is greater then end
            str.getChars(2, 1, array, 0);
        }

        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```
Exception: java.lang.StringIndexOutOfBoundsException: srcBegin > srcEnd

```

**参照:**
[https://docs . Oracle . com/javae/10/docs/API/Java/lang/string buffer . html # get hars(int，int，char%5B%5D，int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuffer.html#getChars(int, int, char%5B%5D, int))