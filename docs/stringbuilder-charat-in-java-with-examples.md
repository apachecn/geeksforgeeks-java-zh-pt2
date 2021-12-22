# Java 中的 StringBuilder charAt()示例

> 原文:[https://www . geeksforgeeks . org/stringbuilder-charat-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuilder-charat-in-java-with-examples/)

**字符串生成器类**的**字符(int index)** 方法用于返回字符串生成器对象包含的字符串的指定索引处的字符。索引值应该介于 0 和 length()-1 之间。

**语法:**

```java
public char charAt(int index)
```

**参数:**该方法接受一个 int 类型参数**索引**，表示要返回的字符的索引。

**返回值:**该方法返回指定位置的**字符。**

**异常:**当索引为负或大于等于长度()时，此方法抛出**indexout of boundsexception**。

以下程序演示了 StringBuilder 类的 charAt()方法:

**例 1:**

```java
// Java program to demonstrate
// the charAt() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        StringBuilder str = new StringBuilder();

        // add the String to StringBuilder Object
        str.append("Geek");

        // get char at position 1
        char ch = str.charAt(1);

        // print the result
        System.out.println("StringBuilder Object"
                           + " contains = " + str);
        System.out.println("Character at Position 1"
                           + " in StringBuilder = " + ch);
    }
}
```

**Output:**

```java
StringBuilder Object contains = Geek
Character at Position 1 in StringBuilder = e

```

**例 2:**

```java
// Java program demonstrate
// the charAt() Method.

class GFG {
    public static void main(String[] args)
    {
        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder
            str
            = new StringBuilder("WelcomeGeeks");

        // print string
        System.out.println("String is "
                           + str.toString());

        // loop through string and print every Character
        for (int i = 0; i < str.length(); i++) {

            // get char at position i
            char ch = str.charAt(i);

            // print char
            System.out.println("Char at position "
                               + i + " is " + ch);
        }
    }
}
```

**Output:**

```java
String is WelcomeGeeks
Char at position 0 is W
Char at position 1 is e
Char at position 2 is l
Char at position 3 is c
Char at position 4 is o
Char at position 5 is m
Char at position 6 is e
Char at position 7 is G
Char at position 8 is e
Char at position 9 is e
Char at position 10 is k
Char at position 11 is s

```

**示例 3:** 演示 IndexOutOfBoundException

```java
// Java program to demonstrate
// IndexOutOfBound exception thrown by the charAt() Method.

class GFG {
    public static void main(String[] args)
    {

        try {

            // create a StringBuilder object
            // with a String pass as parameter
            StringBuilder
                str
                = new StringBuilder("WelcomeGeeks");

            // get char at position i
            char ch = str.charAt(str.length());

            // print char
            System.out.println("Char at position "
                               + str.length() + " is "
                               + ch);
        }

        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
Exception: java.lang.StringIndexOutOfBoundsException:
 String index out of range: 12

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/stringbuilder . html # charAt(int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuilder.html#charAt(int))