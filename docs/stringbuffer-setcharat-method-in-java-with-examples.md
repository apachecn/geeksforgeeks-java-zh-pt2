# Java 中 StringBuffer setCharAt()方法，带示例

> 原文:[https://www . geeksforgeeks . org/stringbuffer-setcharat-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuffer-setcharat-method-in-java-with-examples/)

**StringBuffer 类**的 **setCharAt()** 方法将位置索引处的字符设置为字符，该字符是作为参数传递给方法的值。该方法返回一个与旧序列相同的新序列，唯一不同的是新序列中的位置索引处有一个新字符 ch。索引参数必须大于或等于 0，并且小于 StringBuffer 对象包含的字符串的长度。

**语法:**

```
public void setCharAt(int index, char ch)
```

**参数:**该方法取两个参数:

*   **索引**:整数类型值，指要设置的字符的索引。
*   **ch** :引用新字符的字符类型值。

**返回:**此方法不返回任何内容。

**异常:**如果索引为负或大于长度()，此方法将抛出 IndexOutOfBoundException。

以下程序演示了 StringBuffer 类的 setCharAt()方法

**例 1:**

```
// Java program to demonstrate
// the setCharAt() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer str
            = new StringBuffer("Geeks For Geeks");

        // print string
        System.out.println("String = "
                           + str.toString());

        // set char at index 4 to '0'
        str.setCharAt(7, '0');

        // print string
        System.out.println("After setCharAt() String = "
                           + str.toString());
    }
}
```

**Output:**

```
String = Geeks For Geeks
After setCharAt() String = Geeks F0r Geeks

```

**示例 2:** 演示 IndexOutOfBoundsException。

```
// Java program to demonstrate
// Exception thrown by the setCharAt() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer str
            = new StringBuffer("Geeks for Geeks");

        try {

            // pass index -1
            str.setCharAt(-1, 'T');
        }

        catch (Exception e) {
            System.out.println("Exception:" + e);
        }
    }
}
```

**Output:**

```
Exception:java.lang.StringIndexOutOfBoundsException: String index out of range: -1

```

**参考资料:**
[https://docs . Oracle . com/javae/10/docs/API/Java/lang/string buffer . html # setharat(int，char)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuffer.html#setCharAt(int, char))