# Java 中 StringBuffer trimToSize()方法，带示例

> 原文:[https://www . geeksforgeeks . org/stringbuffer-trimtosize-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuffer-trimtosize-method-in-java-with-examples/)

**字符串填充类**的 **trimToSize()** 方法是用于修剪字符串填充对象的字符序列的容量的内置方法。如果 StringBuffer 对象使用的缓冲区大于保存其当前字符序列所必需的大小，则调用此方法来调整 StringBuffer 对象的大小，以便将此对象转换为空间效率更高的对象。调用此方法可能会影响后续调用 capacity()方法返回的值，但这不是必需的。

**语法:**

```
public void trimToSize()
```

**返回:**此方法不返回任何内容。

下面的程序说明了 StringBuffer.trimToSize()方法:

**例 1:**

```
// Java program to demonstrate
// the trimToSize() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer str
            = new StringBuffer("GeeksForGeeks");

        // add more string to StringBuffer
        str.append("Contribute");

        // print capacity
        System.out.println("Capacity before "
                           + "applying trimToSize() = "
                           + str.capacity());

        // applying trimToSize() Method
        str.trimToSize();

        // print string
        System.out.println("String = " + str.toString());

        // print capacity
        System.out.println("Capacity after"
                           + " applying trimToSize() = "
                           + str.capacity());
    }
}
```

**Output:**

```
Capacity before applying trimToSize() = 29
String = GeeksForGeeksContribute
Capacity after applying trimToSize() = 23

```

**例 2:**

```
// Java program to demonstrate
// the trimToSize() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer str
            = new StringBuffer();

        // add more string to StringBuffer
        str.append("GeeksForGeeks classes");

        // print capacity
        System.out.println("Capacity before"
                           + " applying trimToSize() = "
                           + str.capacity());

        // applying trimToSize() Method
        str.trimToSize();

        // print string
        System.out.println("String = " + str.toString());

        // print capacity
        System.out.println("Capacity after "
                           + "applying trimToSize() = "
                           + str.capacity());
    }
}
```

**Output:**

```
Capacity before applying trimToSize() = 34
String = GeeksForGeeks classes
Capacity after applying trimToSize() = 21

```

**参考资料:**
[https://docs . Oracle . com/javae/10/docs/API/Java/lang/string buffer . html # trimtosize()](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuffer.html#trimToSize())