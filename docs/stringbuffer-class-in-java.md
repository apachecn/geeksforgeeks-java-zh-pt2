# Java 中的 StringBuffer 类

> 原文:[https://www.geeksforgeeks.org/stringbuffer-class-in-java/](https://www.geeksforgeeks.org/stringbuffer-class-in-java/)

**StringBuffer** 是 **String** 的对等类，提供了字符串的大部分功能。该字符串表示固定长度、不可变的字符序列，而 StringBuffer 表示可增长和可写的字符序列。 **StringBuffer** 可以在中间插入字符和子字符串，也可以附加到末尾。它会自动增长，为这种添加腾出空间，并且通常会预分配比实际需要更多的字符，以留出增长空间。

**StringBuffer 类的一些有趣事实**

涂抹时一定要保持在 mi 的后面，具体如下:**T3**

*   java.lang.StringBuffer 扩展(或继承自)[对象类](https://www.geeksforgeeks.org/object-class-in-java/)。
*   StringBuffer 类的所有实现接口:可序列化、可追加、字符序列。
*   公共最终类 StringBuffer 扩展了实现 Serializable、CharSequence、Appendable 的对象。
*   字符串缓冲区对于多线程使用是安全的。这些方法可以在任何需要的地方同步，以便任何特定实例上的所有操作都表现得好像它们以某种顺序发生一样。
*   每当发生涉及源序列的操作(如从源序列追加或插入)时，此类只在执行操作的字符串缓冲区上同步，而不在源上同步。
*   它继承了对象类的一些方法，例如 *clone()，equals()，finalize()，getClass()，hashCode()，*notify()*，notifyAll()。*

> **记住:** StringBuilder **，** J2SE 5 为 Java 已经强大的字符串处理能力增加了一个新的字符串类。这个新类叫做 StringBuilder。它与 StringBuffer 相同，除了一个重要区别:它不是同步的，这意味着它不是线程安全的。StringBuilder 的优点是性能更快。但是，在使用多线程的情况下，必须使用 StringBuffer 而不是 StringBuilder。

**StringBuffer 类的构造函数**

**1。StringBuffer()** :它保留了 16 个字符的空间，无需重新分配

```
StringBuffer s = new StringBuffer();
```

**2。****StringBuffer(int size)**:它接受显式设置缓冲区大小的整数参数。

```
StringBuffer s = new StringBuffer(20);
```

**3。****StringBuffer(String str):**它接受一个字符串参数，该参数设置 StringBuffer 对象的初始内容，并在不重新分配的情况下为 16 个字符保留空间。

```
StringBuffer s = new StringBuffer("GeeksforGeeks");
```

**StringBuffer 类的方法**

<figure class="table">中删除一系列字符

| **Method** | **Action already performed** |
| --- | --- |
| 追加() | Used to add text at the end of existing text. |
| length | The length of the string can be found by the length () method. |
| capacity | Total allocated capacity can be found by capacity () method. |
|  |  |
| delete | Invoke object from |
| 插入() | Inserts text at the specified index position |
| 长度() | Returns the length of the string |
| 反向() | 反向字符串填充器对象内的字符 |
| replace |

</figure>

> **注意:**除此之外，String 类中使用的所有方法也可以使用。Tese 辅助方法如下:

*   [**保障能力()**](https://www.geeksforgeeks.org/stringbuffer-ensurecapacity-method-in-java-with-examples/)

它用于增加 StringBuffer 对象的容量。新容量将设置为我们指定的值或当前容量的两倍加二(即容量+2)，以较大者为准。这里，容量指定了缓冲区的大小。

**语法:**

```
void ensureCapacity(int capacity)
```

*   [**appendCodePoint(int CodePoint)**](https://www.geeksforgeeks.org/stringbuffer-appendcodepoint-method-in-java/)**:**这个方法将 codePoint 参数的字符串表示形式追加到这个序列中。

**语法:**

```
public StringBuffer appendCodePoint(int codePoint)
```

*   **charAt(int index)**

此方法返回该序列中指定索引处的字符值。

**语法:**

```
public char charAt(int index)
```

*   **IntStream chars()** :这个方法返回一个 int 零扩展的字符值流。

**语法:**

```
public IntStream chars()
```

*   [**int codePointAt(int index)**](https://www.geeksforgeeks.org/stringbuffer-codepointat-method-in-java-with-examples/):此方法返回指定索引处的字符(Unicode 码位)。

**语法:**

```
public int codePointAt(int index)
```

*   [**int codepoint before(int index)**](https://www.geeksforgeeks.org/stringbuffer-codepointbefore-method-in-java-with-examples/):此方法返回指定索引前的字符(Unicode 码位)。

**语法:**

```
public int codePointBefore(int index)
```

*   [**int codePointCount(int beginIndex，int endIndex)**](https://www.geeksforgeeks.org/stringbuffer-codepointcount-method-in-java-with-examples/) :该方法返回该序列指定文本范围内的 Unicode 码点数。

**语法:**

```
public int codePointCount(int beginIndex, int endIndex)
```

*   **IntStream codePoints()** :这个方法从这个序列返回一个代码点值流。

**语法:**

```
public IntStream codePoints()
```

*   [**void getChars(int srcBegin，int srcEnd，char[] dst，int dstBegin)**](https://www.geeksforgeeks.org/stringbuffer-getchars-method-in-java-with-examples/) :在这个方法中，字符从这个序列复制到目的字符数组 dst 中。

**语法:**

```
public void getChars(int srcBegin, int srcEnd, char[] dst, int dstBegin)
```

*   [**int index of(String str)**](https://www.geeksforgeeks.org/stringbuffer-indexof-method-in-java-with-examples/):这个方法返回这个字符串中第一个出现的指定子字符串的索引。

**语法:**

```
public int indexOf(String str)
public int indexOf(String str, int fromIndex)
```

*   [**int LastIndex of(String str)**](https://www.geeksforgeeks.org/stringbuffer-lastindexof-method-in-java-with-examples/):这个方法返回这个字符串中指定子字符串最后一次出现的索引。

**语法:**

```
public int lastIndexOf(String str)
public int lastIndexOf(String str, int fromIndex)
```

*   [**int offset by codepoints(int index，int codePointOffset)**](https://www.geeksforgeeks.org/stringbuffer-offsetbycodepoints-method-in-java-with-examples/) :该方法返回该序列内的索引，该索引从给定索引偏移了 codePointOffset 代码点。

**语法:**

```
public int offsetByCodePoints(int index, int codePointOffset) 
```

*   [**void setCharAt(int index，char ch)**](https://www.geeksforgeeks.org/stringbuffer-setcharat-method-in-java-with-examples/) :在这个方法中，指定索引处的字符设置为 ch。

**语法:**

```
public void setCharAt(int index, char ch)
```

*   [**void setLength(int newLength)**](https://www.geeksforgeeks.org/stringbuffer-setlength-in-java-with-examples/):此方法设置字符序列的长度。

**语法:**

```
public void setLength(int newLength)
```

*   [**字符序列子序列(int start，int end)**](https://www.geeksforgeeks.org/stringbuffer-subsequence-in-java-with-examples/) :这个方法返回一个新的字符序列，它是这个序列的子序列。

**语法:**

```
public CharSequence subSequence(int start, int end)
```

*   [**字符串子串(int start)**](https://www.geeksforgeeks.org/stringbuffer-substring-method-in-java-with-examples/) :这个方法返回一个新的 String，它包含当前包含在这个字符序列中的字符的子序列。

**语法:**

```
public String substring(int start)
public String substring(int start,int end)
```

*   [**String toString()**](https://www.geeksforgeeks.org/stringbuffer-tostring-method-in-java-with-examples/) :这个方法返回一个代表这个序列中数据的字符串。

**语法:**

```
public String toString()
```

*   [**void trimToSize()**](https://www.geeksforgeeks.org/stringbuffer-trimtosize-method-in-java-with-examples/) :此方法试图减少字符序列使用的存储量。

**语法:**

```
public void trimToSize()
```

> 上面我们只讨论了最广泛使用的方法，并对它们进行了严格的限制，因为它们在编程爱好者中广泛使用。

**实施:**

**例 1:** *长度()和容量()*方法

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate StringBuffer class
// via length() and capacity() methods

// Importing I/O classes
import java.io.*;

// Main class
class GFG {

    // main driver method
    public static void main(String[] args)
    {

        // Creating adn storing string by creating object of
        // StringBuffer
        StringBuffer s = new StringBuffer("GeeksforGeeks");

        // Getting the length of the string
        int p = s.length();

        // Getting the capacity of the string
        int q = s.capacity();

        // Printing the length and capacity of
        // above generated input string on console
        System.out.println("Length of string GeeksforGeeks="
                           + p);
        System.out.println(
            "Capacity of string GeeksforGeeks=" + q);
    }
}
```

**Output**

```
Length of string GeeksforGeeks=13
Capacity of string GeeksforGeeks=29
```

**例 2:** [**追加()**](https://www.geeksforgeeks.org/stringbuffer-append-method-in-java-with-examples/)

它用于在现有文本的末尾添加文本。

以下是它的几种形式:

```
StringBuffer append(String str)
StringBuffer append(int num)
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate StringBuffer class
// via append() method

// Importing required classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of StringBuffer class and
        // passing random string
        StringBuffer s = new StringBuffer("Geeksfor");

        // Usage of append() method
        s.append("Geeks");

        // Returns GeeksforGeeks
        System.out.println(s);

        s.append(1);
        // Returns GeeksforGeeks1
        System.out.println(s);
    }
}
```

**Output**

```
GeeksforGeeks
GeeksforGeeks1
```

**例 3:** [**插入()**](https://www.geeksforgeeks.org/stringbuffer-insert-java/)

它用于在指定的索引位置插入文本。

**语法:**以下是它的几个例子:

```
StringBuffer insert(int index, String str)
StringBuffer insert(int index, char ch)
```

这里，*索引*指定了字符串将插入调用 **StringBuffer** 对象的索引。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate StringBuffer class
// via insert() method

// Importing required I/O classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of StringBuffer class
        StringBuffer s = new StringBuffer("GeeksGeeks");

        // Inserting element and posistion as an arguments
        s.insert(5, "for");
        // Returns GeeksforGeeks
        System.out.println(s);

        s.insert(0, 5);
        // Returns 5GeeksforGeeks
        System.out.println(s);

        s.insert(3, true);
        // Returns 5GetrueeksforGeeks
        System.out.println(s);

        s.insert(5, 41.35d);
        // Returns 5Getr41.35ueeksforGeeks
        System.out.println(s);

        s.insert(8, 41.35f);
        // Returns 5Getr41.41.3535ueeksforGeeks
        System.out.println(s);

        // Declaring and initializing character array
        char geeks_arr[] = { 'p', 'a', 'w', 'a', 'n' };

        // Inserting character array at offset 9
        s.insert(2, geeks_arr);
        // Returns 5Gpawanetr41.41.3535ueeksforGeeks
        System.out.println(s);
    }
}
```

**Output:** 

```
GeeksforGeeks
5GeeksforGeeks
5GetrueeksforGeeks
5Getr41.35ueeksforGeeks
5Getr41.41.3535ueeksforGeeks
5Gpawanetr41.41.3535ueeksforGeeks
```

**例 4:** [**反向()**](https://www.geeksforgeeks.org/stringbuffer-reverse-method-in-java/)

它可以使用**反转( )来反转 StringBuffer 对象中的字符。**此方法返回调用它的反向对象。**T3】**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate StringBuffer class
// via reverse() method

// Importing I/O classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a string via creating
        // object of StringBuffer class
        StringBuffer s = new StringBuffer("GeeksGeeks");

        // Invoking reverse() method
        s.reverse();

        // Returns "skeeGrofskeeG"
        System.out.println(s);
    }
}
```

**Output**

```
skeeGskeeG
```

**例 5:** [**删除()**](https://www.geeksforgeeks.org/stringbuffer-delete-method-in-java-with-examples/) **和** [**删除 CharAt()**](https://www.geeksforgeeks.org/stringbuffer-deletecharat-method-in-java/)

它可以使用 **delete( )** 和 **deleteCharAt( )** 方法删除字符串缓冲区中的字符。 **delete( )** 方法从调用对象中删除一系列字符。这里，起始索引指定要删除的第一个字符的索引，结束索引指定要删除的最后一个字符之后一个字符的索引。因此，删除的子字符串从起始索引运行到 endIndex–1。返回生成的 StringBuffer 对象。 **deleteCharAt( )** 方法删除 *loc 指定索引处的字符。*它返回结果 StringBuffer 对象。

**语法:**

```
StringBuffer delete(int startIndex, int endIndex)
StringBuffer deleteCharAt(int loc)
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate StringBuffer class
// via delete() and deleteCharAt() Methods

// Importing I/O classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        StringBuffer s = new StringBuffer("GeeksforGeeks");

        s.delete(0, 5);
        // Returns forGeeks
        System.out.println(s);

        s.deleteCharAt(7);
        // Returns forGeek
        System.out.println(s);
    }
}
```

**Output**

```
forGeeks
forGeek
```

**例 6:** [**替换()**](https://www.geeksforgeeks.org/stringbuffer-replace-method-in-java-with-examples/)

它可以通过调用 replace()将 StringBuffer 对象中的一组字符替换为另一组字符。被替换的子字符串由索引开始索引和结束索引指定。因此，从索引开始到 endIndex–1 的子字符串被替换。替换字符串以字符串形式传递。返回生成的 StringBuffer 对象。

**语法:**

```
StringBuffer replace(int startIndex, int endIndex, String str)
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate StringBuffer class
// via replace() method

// Importing I/O classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        StringBuffer s = new StringBuffer("GeeksforGeeks");
        s.replace(5, 8, "are");

        // Returns GeeksareGeeks
        System.out.println(s);
    }
}
```

**Output**

```
GeeksareGeeks
```

本文由**罗克丝·托瓦尔供稿。**如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。