# Java 中字符串类 stripLeading()方法示例

> 原文:[https://www . geesforgeks . org/string-class-strip leading-method-in-Java-with-examples/](https://www.geeksforgeeks.org/string-class-stripleading-method-in-java-with-examples/)

String Class stripLeading()方法用于从字符串中去除前导空格，即 **stripLeading()** 方法仅删除字符串开头的所有空格。

**示例:**

```
Input:

String name = "   kapil   ";
System.out.println("#" + name + "#);
System.out.println("#" + name.stripLeading());

Output:

#   kapil   #
#kapil   # // Leading whitespaces are removed 
```

**语法:**

```
public String stripLeading()
```

**返回:**删除字符串开头所有空格后的字符串。

> ***注意:**像 java 中的 stripTrailing()方法一样，我们有 strip()(移除前导和尾随空格)和 stripLeading()(移除唯一的前导空格)。*

下面是问题陈述的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the usage of
// stripLeading() method in comparison to
// other methods

class GFG {
    public static void main(String[] args)
    {

        // creating a string
        String str = " Hello, World ";

        // print the string without any function
        System.out.println("String is");
        System.out.println("#" + str + "#");
        System.out.println();

        // using strip() method
        System.out.println("Using strip()");
        System.out.println("#" + str.strip() + "#");
        System.out.println();

        // using stripLeading() method
        System.out.println("Using stripLeading()");
        System.out.println("#" + str.stripLeading() + "#");
        System.out.println();

        // using stripTrailing() method
        System.out.println("Using stripTrailing()");
        System.out.println("#" + str.stripTrailing() + "#");
    }
}
```

**输出:**

```
String is
#  Hello,  World #

Using strip()
#Hello,  World#

Using stripLeading()
#Hello,  World #

Using stripTrailing()
#  Hello,  World#
```