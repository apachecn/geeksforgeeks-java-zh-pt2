# Java 中的 StringBuilder offset by codepoints()方法，示例

> 原文:[https://www . geeksforgeeks . org/stringbuilder-offsetbycodepoints-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuilder-offsetbycodepoints-method-in-java-with-examples/)

**StringBuilder 类**的 **offsetByCodePoints()** 方法返回 StringBuilder 包含的字符串中的索引，该索引与 codePointOffset 代码点作为参数传递的索引有所偏移。不成对的代理位于索引和代码点偏移量之间，每个偏移量代表一个代码点。

**语法:**

```
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

下面的程序演示了 StringBuilder 类的 offsetByCodePoints()方法:

**例 1:**

```
// Java program to demonstrate
// the offsetByCodePoints() Method.

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

        // returns the index within this sequence
        int returnvalue = str.offsetByCodePoints(1, 4);

        // prints the index
        System.out.println("Index = " + returnvalue);
    }
}
```

**Output:**

```
String = WelcomeGeeks
Index = 5

```

**例 2:**

```
// Java program to demonstrate
// the offsetByCodePoints() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder
            str
            = new StringBuilder("India Is great");

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

```
String = India Is great
Index = 11

```

**示例 3:** 演示 IndexOutOfBoundException

```
// Java program to demonstrate
// Exception thrown by offsetByCodePoints() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder
            str
            = new StringBuilder("India");

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

```
Exception: java.lang.IndexOutOfBoundsException

```

**参考:**
[https://docs . Oracle . com/javae/10/docs/API/Java/lang/string builder . html # offsetbycode points(int，int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuilder.html#offsetByCodePoints(int, int))