# Java 中的 StringJoiner 类

> 原文:[https://www.geeksforgeeks.org/stringjoiner-class-in-java/](https://www.geeksforgeeks.org/stringjoiner-class-in-java/)

StringJoiner 是 java.util 包中的一个类，用于构造由分隔符分隔的字符(字符串)序列，可选地以提供的前缀开始，以给定的后缀结束。虽然这也可以在 StringBuilder 类的帮助下完成，即在每个字符串后添加分隔符，但 StringJoiner 提供了一种简单的方法来实现这一点，而无需编写太多代码。

### 字符串连接类的构造函数

**1。StringJoiner(CharSequence 分隔符):**它构造一个 StringJoiner，没有字符，没有前缀或后缀，还有一个提供的分隔符的副本。

**语法:**

```java
public StringJoiner(CharSequence delimiter)
```

**参数:**添加到 StringJoiner 值的每个元素之间要使用的字符序列

**异常抛出:** [空指针异常](http://www.geeksforgeeks.org/null-pointer-exception-in-java/)如果分隔符为空

**2。StringJoiner(字符序列分隔符，** **字符序列前缀，** **字符序列后缀):**它使用所提供的前缀、分隔符和后缀的副本来构造没有字符的字符串 Joiner。如果没有字符被添加到 StringJoiner 中，并且调用了访问字符串值的方法，它将在结果中返回前缀+后缀(或其属性)，除非首先调用了 *setEmptyValue* 。

**语法:**

```java
public StringJoiner(CharSequence delimiter, CharSequence prefix, CharSequence suffix)
```

**参数:**

*   The sequence of characters to be used between each element is added to the StringJoiner value.
*   The character sequence to start with.
*   The character sequence to be used at the end.

**异常抛出:** [空指针异常](http://www.geeksforgeeks.org/null-pointer-exception-in-java/)如果前缀、分隔符或后缀为空。

### 字符串连接类的方法

<figure class="table">

| 方法 | 执行的操作 |
| --- | --- |
| [添加()](https://www.geeksforgeeks.org/stringjoiner-add-method-in-java/) | 添加给定字符序列值的副本作为字符串连接值的下一个元素。如果新元素为空，则添加“空”。 |
| [length()](https://www.geeksforgeeks.org/stringjoiner-length-method-in-java/) | 返回此 StringJoiner 的字符串表示形式的长度。 |
| [merge()](https://www.geeksforgeeks.org/stringjoiner-merge-method-in-java/) | 如果给定 StringJoiner 的内容不为空，则将其添加为下一个元素。如果给定的 StringJoiner 为空，则调用无效。假设另一个字符串连接器使用了不同的分隔符。在这种情况下，来自其他 StringJoiner 的元素与该分隔符连接在一起，结果作为单个元素附加到该 StringJoiner。 |
| [toString()](https://www.geeksforgeeks.org/stringjoiner-tostring-method-in-java/) | 返回此 StringJoiner 的 String 对象 |
| [setEmptyValue()](https://www.geeksforgeeks.org/stringjoiner-setemptyvalue-method-in-java/) | 设置确定此 StringJoiner 的字符串表示时要使用的字符串，目前还没有添加元素；也就是当它为空时 |

</figure>

[](toString() method)**例:**

## Java

```java
// Java program to Demonstrate Methods
// of StringJoiner class

// Importing required classes
import java.util.ArrayList;
import java.util.StringJoiner;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an empty ArrayList of string type
        ArrayList<String> al = new ArrayList<>();

        // Adding elements to above List
        al.add("Ram");
        al.add("Shyam");
        al.add("Alice");
        al.add("Bob");

        // Creating object of class inside main()
        StringJoiner sj1 = new StringJoiner(",");

        // setEmptyValue() method
        sj1.setEmptyValue("sj1 is empty");
        System.out.println(sj1);

        // add() method
        sj1.add(al.get(0)).add(al.get(1));
        System.out.println(sj1);

        // length() method
        System.out.println("Length of sj1 : "
                           + sj1.length());

        StringJoiner sj2 = new StringJoiner(":");
        sj2.add(al.get(2)).add(al.get(3));

        // merge() method
        sj1.merge(sj2);

        // toString() method
        System.out.println(sj1.toString());

        System.out.println("Length of new sj1 : "
                           + sj1.length());
    }
}
```

**输出**

```java
sj1 is empty
Ram,Shyam
Length of sj1 : 9
Ram,Shyam,Alice:Bob
Length of new sj1 : 19
```

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。