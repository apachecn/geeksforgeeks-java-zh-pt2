# Java 中的 StringBuilder deleteCharAt()示例

> 原文:[https://www . geeksforgeeks . org/stringbuilder-delete charat-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuilder-deletecharat-in-java-with-examples/)

**字符串生成器类**的 **deleteCharAt(int index)** 方法从字符串生成器包含的字符串中删除给定索引处的字符。该方法将索引作为一个参数，该参数代表我们要移除的字符的索引，并将剩余的字符串作为 StringBuilder 对象返回。应用此方法后，该字符串生成器缩短了一个字符。

**语法:**

```java
public StringBuilder deleteCharAt(int index)
```

**参数:**这个方法接受一个参数**索引**代表你想要删除的字符的索引。

**返回值:**该方法在移除字符后返回**这个 StringBuilder 对象**。

**异常:**如果索引小于零，或者索引大于字符串的长度，则该方法抛出**StringIndexOutOfBoundsException**。

下面的程序演示了 StringBuilder 类的 deleteCharAt()方法:

**例 1:**

```java
// Java program to demonstrate
// the deleteCharAt() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder
            str
            = new StringBuilder("WelcomeGeeks");

        // print string
        System.out.println("Before removal String = "
                           + str.toString());

        // remove the Character from index 8
        StringBuilder afterRemoval = str.deleteCharAt(8);

        // print string after removal of Character
        System.out.println("After removal of character"
                           + " at index 8 = "
                           + afterRemoval.toString());
    }
}
```

**Output:**

```java
Before removal String = WelcomeGeeks
After removal of character at index 8 = WelcomeGeks

```

**例 2:**

```java
// Java program to demonstrate
// the deleteCharAt() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder
            str
            = new StringBuilder("GeeksforGeeks");

        // print string
        System.out.println("Before removal String = "
                           + str.toString());

        // remove the Character from index 3
        str = str.deleteCharAt(3);

        // print string after removal of Character
        System.out.println("After removal of Character"
                           + " from index=3"
                           + " String becomes => "
                           + str.toString());

        // remove the substring from index 5
        str = str.deleteCharAt(5);

        // print string after removal of Character
        System.out.println("After removal of Character"
                           + " from index=5"
                           + " String becomes => "
                           + str.toString());
    }
}
```

**Output:**

```java
Before removal String = GeeksforGeeks
After removal of Character from index=3 String becomes => GeesforGeeks
After removal of Character from index=5 String becomes => GeesfrGeeks

```

**示例 3:** 演示 IndexOutOfBoundException

```java
// Java program to demonstrate
// exception thrown by the deleteCharAt() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder
            str
            = new StringBuilder("evil dead_01");

        try {

            // make index > length of String
            StringBuilder
                afterRemoval
                = str.deleteCharAt(14);
        }

        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
Exception: java.lang.StringIndexOutOfBoundsException: String index out of range: 14

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/stringbuilder . html # delete charat(int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuilder.html#deleteCharAt(int))