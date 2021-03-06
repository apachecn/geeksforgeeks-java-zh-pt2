# Java 中的 StringBuffer offsetByCodePoints()方法，示例

> 原文:[https://www . geeksforgeeks . org/stringbuffer-offsetbycodepoints-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuffer-offsetbycodepoints-method-in-java-with-examples/)

**StringBuffer 类**的 **offsetByCodePoints()** 方法返回 StringBuffer 包含的字符串中的索引，该索引与 codePointOffset 代码点作为参数传递的索引有偏移。不成对的代理位于索引和代码点偏移量之间，每个偏移量代表一个代码点。

**语法:**

```java
public int offsetByCodePoints(int index,
                       int codePointOffset)
```

**参数:**该方法取两个参数:

*   **索引**:要偏移的索引
*   **代码点偏移量**:代码点的偏移量

**返回值:**该方法返回**该序列内的指数**。

**异常:**如果以下任一项为真，此方法将抛出**指数超出边界异常**:

*   索引< 0 or index >序列的长度。
*   代码点偏移量> 0，以索引开始的子序列的代码点少于代码点偏移量
*   codePointOffset

下面的程序演示了 StringBuffer 类的 offsetByCodePoints()方法:

**例 1:**

```java
// Java program to demonstrate
// the offsetByCodePoints() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer
            str
            = new StringBuffer("WelcomeGeeks");

        // print string
        System.out.println("String = "
                           + str.toString());

        // returns the index within this sequence
        int returnvalue = str.offsetByCodePoints(1, 4);

        // prints the index
        System.out.println("Index = " + returnvalue);
    }
}
```

**Output:**

```java
String = WelcomeGeeks
Index = 5

```

**例 2:**

```java
// Java program to demonstrate
// the offsetByCodePoints() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer
            str
            = new StringBuffer("India Is great");

        // print string
        System.out.println("String = " + str.toString());

        // returns the index within this sequence
        int returnvalue = str.offsetByCodePoints(2, 9);

        // prints the index
        System.out.println("Index = " + returnvalue);
    }
}
```

**Output:**

```java
String = India Is great
Index = 11

```

**示例 3:** 演示 IndexOutOfBoundException

```java
// Java program to demonstrate
// Exception thrown by offsetByCodePoints() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        // with a String pass as parameter
        StringBuffer
            str
            = new StringBuffer("India");

        try {

            // returns the index within this sequence
            int returnvalue = str.offsetByCodePoints(2, 9);

            // prints the index
            System.out.println("Index = " + returnvalue);
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
Exception: java.lang.IndexOutOfBoundsException

```

**参考:**
[https://docs . Oracle . com/javae/10/docs/API/Java/lang/string buffer . html # offsetbycode points(int，int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuffer.html#offsetByCodePoints(int, int))