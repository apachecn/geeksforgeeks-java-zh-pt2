# Java 中 StringBuilder delete()示例

> 原文:[https://www . geeksforgeeks . org/stringbuilder-delete-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuilder-delete-in-java-with-examples/)

StringBuilder 类的 **delete(int start，int end)** 方法从 StringBuilder 包含的字符串中删除从索引开始到索引结束-1 的字符。此方法将两个索引作为参数首先 start 表示第一个字符的索引，endIndex 表示要从 stringBuilder 包含的 String 中移除的子字符串的最后一个字符之后的索引，并将剩余的 String 作为 StringBuilder 对象返回。

**语法:**

```java
public StringBuilder delete(int start, int end)
```

**参数:**该方法接受两个参数:

*   **开始**:子串第一个字符的索引。
*   **end** :子串最后一个字符后的索引。

**返回值:**这个方法在去掉子串后返回**这个 StringBuilder 对象**。

**异常:**如果开始小于零，或者开始大于字符串长度，或者开始大于结束，该方法抛出**StringIndexOutOfBoundsException**。

下面的程序演示了 StringBuilder 类的 delete()方法:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// the delete() Method.

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

        // remove the substring from index 2 to 8
        StringBuilder afterRemoval = str.delete(2, 8);

        // print string after removal of substring
        System.out.println("After removal String = "
                           + afterRemoval.toString());
    }
}
```

**Output**

```java
Before removal String = WelcomeGeeks
After removal String = Weeeks
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// the delete() Method.

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

        // remove the substring from index 8 to 8
        StringBuilder afterRemoval = str.delete(8, 8);

        // start equal to end so no change in string
        // print string after removal of substring
        System.out.println("After removal of SubString"
                           + " start=8 to end=8"
                           + " String becomes => "
                           + afterRemoval.toString());

        // remove the substring from index 1 to 8
        afterRemoval = str.delete(1, 8);

        // print string after removal of substring
        System.out.println("After removal of SubString"
                           + " start=1 to end=8"
                           + " String becomes => "
                           + afterRemoval.toString());
    }
}
```

**Output:** 

```java
Before removal String = GeeksforGeeks
After removal of SubString start=8 to end=8 String becomes => GeeksforGeeks
After removal of SubString start=1 to end=8 String becomes => GGeeks
```

**示例 3:** 演示 IndexOutOfBoundException

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// exception thrown by the delete() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        // with a String pass as parameter
        StringBuilder
            str
            = new StringBuilder("GeeksforGeeks");

        try {

            // make start greater than end
            StringBuilder afterRemoval = str.delete(7, 4);
        }

        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:** 

```java
Exception: java.lang.StringIndexOutOfBoundsException
```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/stringbuilder . html # delete(int，int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuilder.html#delete(int, int))