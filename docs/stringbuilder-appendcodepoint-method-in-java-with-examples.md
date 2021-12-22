# Java 中的 StringBuilder appendCodePoint()方法，带示例

> 原文:[https://www . geeksforgeeks . org/stringbuilder-appendcodepoint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuilder-appendcodepoint-method-in-java-with-examples/)

**字符串构建器类**的**appendCodePoint(int CodePoint)**方法是用于将 codePoint 参数的字符串表示追加到该序列的内置方法。
参数被附加到这个字符串构建器内容中，对象的长度增加了字符字符计数(代码点)。效果就像参数中的 int 值被转换为 char 数组，然后该数组中的字符被追加到该字符序列中一样。
**语法:**

```
public StringBuilder appendCodePoint(int codePoint)
```

**参数:**该方法只接受一个参数**码点**，该参数为整型值，指的是一个 Unicode 码点。
**返回值:**该方法返回对该对象的**引用。**
下面的程序说明了 Java . lang . stringbuilder . appendcodepoint()方法:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate the
// appendCodePoint(int codePoint)

import java.lang.*;

public class Geeks {
    public static void main(String[] args)
    {

        // create StringBuilder object
        StringBuilder
            str
            = new StringBuilder("GeeksforGeeks");
        System.out.println("StringBuilder = "
                           + str);

        // Append 'C'(67) to the String
        str.appendCodePoint(67);

        // Print the modified String
        System.out.println("Modified StringBuilder = "
                           + str);
    }
}
```

**Output:** 

```
StringBuilder = GeeksforGeeks
Modified StringBuilder = GeeksforGeeksC
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate the
// appendCodePoint(int codePoint)

import java.lang.*;

public class Geeks {
    public static void main(String[] args)
    {

        // create StringBuilder object
        StringBuilder
            str
            = new StringBuilder("GeeksforGeeks");
        System.out.println("StringBuilder = "
                           + str);

        // Append ', '(44) to the String
        str.appendCodePoint(44);

        // Print the modified String
        System.out.println("Modified StringBuilder = "
                           + str);
    }
}
```

**Output:** 

```
StringBuilder = GeeksforGeeks
Modified StringBuilder = GeeksforGeeks,
```

**参考资料:**[https://docs . Oracle . com/javae/7/docs/API/Java/lang/string builder . html # appendcode point(int)](https://docs.oracle.com/javase/7/docs/api/java/lang/StringBuilder.html#appendCodePoint(int))