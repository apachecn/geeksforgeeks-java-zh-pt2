# Java 中的 StringBuilder 类，示例

> 原文:[https://www . geeksforgeeks . org/stringbuilder-class-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuilder-class-in-java-with-examples/)

Java 中的**字符串生成器**代表一个可变的字符序列。因为 Java 中的字符串类创建了一个不可变的字符序列，所以 StringBuilder 类提供了一个字符串类的替代，因为它创建了一个可变的字符序列。StringBuilder 的功能与 StringBuffer 类非常相似，因为两者都提供了一种字符串类的替代方法，即创建一个可变的字符序列。然而，基于同步，StringBuilder 类不同于 StringBuffer 类。StringBuilder 类不能保证同步，而 StringBuffer 类可以。因此，这个类被设计为在 StringBuffer 被一个单独的线程使用的地方作为 StringBuffer 的插入式替换(通常情况下)。在可能的情况下，建议优先使用这个类而不是 StringBuffer，因为在大多数实现中它会更快。StringBuilder 的实例对于多线程使用来说并不安全。如果需要这样的同步，那么建议使用 StringBuffer。
**等级等级:**

```
java.lang.Object
 ↳ java.lang
    ↳ Class StringBuilder
```

**语法:**

```
public final class StringBuilder
    extends Object
    implements Serializable, CharSequence
```

**Java StringBuilder 中的构造函数:**

*   **StringBuilder():** 构造一个字符串生成器，其中没有字符，初始容量为 16 个字符。

*   **StringBuilder(int capacity):**构造一个字符串生成器，其中没有字符，初始容量由 capacity 参数指定。

*   **字符串构建器(字符序列序列):**构建包含与指定字符序列相同字符的字符串构建器。

*   **字符串构建器(String str):** 构建一个初始化为指定字符串内容的字符串构建器。

下面是一个用 Java 说明 StringBuilder 的示例程序:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate StringBuilder

import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        // create a StringBuilder object
        // using StringBuilder() constructor
        StringBuilder str
            = new StringBuilder();

        str.append("GFG");

        // print string
        System.out.println("String = "
                           + str.toString());

        // create a StringBuilder object
        // using StringBuilder(CharSequence) constructor
        StringBuilder str1
            = new StringBuilder("AAAABBBCCCC");

        // print string
        System.out.println("String1 = "
                           + str1.toString());

        // create a StringBuilder object
        // using StringBuilder(capacity) constructor
        StringBuilder str2
            = new StringBuilder(10);

        // print string
        System.out.println("String2 capacity = "
                           + str2.capacity());

        // create a StringBuilder object
        // using StringBuilder(String) constructor
        StringBuilder str3
            = new StringBuilder(str1.toString());

        // print string
        System.out.println("String3 = "
                           + str3.toString());
    }
}
```

**Output:** 

```
String = GFG
String1 = AAAABBBCCCC
String2 capacity = 10
String3 = AAAABBBCCCC
```

**Java StringBuilder 中的方法:**

1.  [**StringBuilder append(X X)**](https://www.geeksforgeeks.org/stringbuilder-append-method-in-java-with-examples/):这个方法将 X 类型参数的字符串表示形式追加到序列中。

2.  [**StringBuilder appendCodePoint(int CodePoint)**](https://www.geeksforgeeks.org/stringbuilder-appendcodepoint-method-in-java-with-examples/):这个方法将 codePoint 参数的字符串表示形式追加到这个序列中。

3.  [**【int capacity()**](https://www.geeksforgeeks.org/stringbuilder-capacity-in-java-with-examples/):此方法返回当前容量。

4.  [**char charAt(int index)**](https://www.geeksforgeeks.org/stringbuilder-charat-in-java-with-examples/):这个方法返回这个序列中指定索引处的 char 值。

5.  **IntStream chars()** :这个方法返回一个 int 零扩展的字符值流。

6.  [**int codePointAt(int index)**](https://www.geeksforgeeks.org/stringbuilder-codepointat-in-java-with-examples/):此方法返回指定索引处的字符(Unicode 码位)。

7.  [**int codepoint before(int index)**](https://www.geeksforgeeks.org/stringbuilder-codepointbefore-in-java-with-examples/):此方法返回指定索引前的字符(Unicode 码位)。

8.  [**int codePointCount(int beginIndex，int endIndex)**](https://www.geeksforgeeks.org/stringbuilder-codepointcount-in-java-with-examples/) :该方法返回该序列指定文本范围内的 Unicode 码点数。

9.  **IntStream codePoints()** :这个方法从这个序列返回一个代码点值流。

10.  [**StringBuilder delete(int start，int end)**](https://www.geeksforgeeks.org/stringbuilder-delete-in-java-with-examples/) :这个方法删除这个序列的子串中的字符。

11.  **StringBuilder delete charat(int index)**:这个方法删除这个序列中指定位置的字符。

12.  [**void ensureCapacity(int minimummcapacity)**](https://www.geeksforgeeks.org/stringbuilder-ensurecapacity-in-java-with-examples/):此方法确保容量至少等于指定的最小值。

13.  [**void getChars(int srcBegin，int srcEnd，char【】dst，int dstBegin)**](https://www.geeksforgeeks.org/stringbuilder-getchars-in-java-with-examples/) :此方法将字符从该序列复制到目标字符数组 dst 中。

14.  [**int indexOf()**](https://www.geeksforgeeks.org/stringbuilder-indexof-method-in-java-with-examples/) :此方法返回指定子串第一次出现的字符串内的索引。

15.  **StringBuilder insert(int offset，boolean b)** :这个方法将 booalternatelean 参数的字符串表示形式插入到这个序列中。

16.  **StringBuilder insert()** :这个方法将 char 参数的字符串表示插入到这个序列中。

17.  [**int lastIndexOf()**](https://www.geeksforgeeks.org/stringbuilder-lastindexof-method-in-java-with-examples/) :此方法返回指定子串最后一次出现的字符串内的索引。

18.  [**int length()**](https://www.geeksforgeeks.org/stringbuilder-length-in-java-with-examples/) :此方法返回长度(字符数)。

19.  **int offset by codepoints(int index，int codePointOffset)** :此方法返回此序列内的索引，该索引从给定索引偏移了 codePointOffset 代码点。

20.  [**StringBuilder replace(int start，int end，String str)**](https://www.geeksforgeeks.org/stringbuilder-replace-in-java-with-examples/) :这个方法用指定 String 中的字符替换这个序列的子串中的字符。

21.  [**StringBuilder reverse()**](https://www.geeksforgeeks.org/stringbuilder-reverse-in-java-with-examples/):这个方法会让这个字符序列被序列的反码替换。

22.  [**void setCharAt(int index，char ch)**](https://www.geeksforgeeks.org/stringbuilder-setcharat-in-java-with-examples/) :在这个方法中，指定索引处的字符设置为 ch。

23.  [**void setLength(int newLength)**](https://www.geeksforgeeks.org/stringbuilder-setlength-in-java-with-examples/):此方法设置字符序列的长度。

24.  [**字符序列子序列(int start，int end)**](https://www.geeksforgeeks.org/stringbuilder-subsequence-in-java-with-examples/) :这个方法返回一个新的字符序列，它是这个序列的子序列。

25.  [**String substring()**](https://www.geeksforgeeks.org/stringbuilder-substring-method-in-java-with-examples/):这个方法返回一个新的 String，它包含当前包含在这个字符序列中的字符的子序列。

26.  [**String toString()**](https://www.geeksforgeeks.org/stringbuilder-tostring-method-in-java-with-examples/) :这个方法返回一个代表这个序列中数据的字符串。

27.  [**void trimToSize()**](https://www.geeksforgeeks.org/stringbuilder-trimtosize-method-in-java-with-examples/) :此方法试图减少字符序列使用的存储量。

**例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate
// methods of StringBuilder

import java.util.*;
import java.util.concurrent.LinkedBlockingQueue;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder str
            = new StringBuilder("AAAABBBCCCC");

        // print string
        System.out.println("String = "
                           + str.toString());

        // reverse the string
        StringBuilder reverseStr = str.reverse();

        // print string
        System.out.println("Reverse String = "
                           + reverseStr.toString());

        // Append ', '(44) to the String
        str.appendCodePoint(44);

        // Print the modified String
        System.out.println("Modified StringBuilder = "
                           + str);

        // get capacity
        int capacity = str.capacity();

        // print the result
        System.out.println("StringBuilder = " + str);
        System.out.println("Capacity of StringBuilder = "
                           + capacity);
    }
}
```

**Output:** 

```
String = AAAABBBCCCC
Reverse String = CCCCBBBAAAA
Modified StringBuilder = CCCCBBBAAAA,
StringBuilder = CCCCBBBAAAA,
Capacity of StringBuilder = 27
```

**参考**:[https://docs . Oracle . com/javase/9/docs/API/Java/lang/stringbuilder . html](https://docs.oracle.com/javase/9/docs/api/java/lang/StringBuilder.html)