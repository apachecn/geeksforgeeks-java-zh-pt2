# 在 Java 中替换字符串中特定索引处的字符

> 原文:[https://www . geesforgeks . org/replace-a-a-character-at-specific-index-in-a-string-in-Java/](https://www.geeksforgeeks.org/replace-a-character-at-a-specific-index-in-a-string-in-java/)

给定一个字符串，任务是在 Java 中替换该字符串中特定索引处的一个字符。

**示例:**

```java
Input: String = "Geeks Gor Geeks", index = 6, ch = 'F'
Output: "Geeks For Geeks."

Input: String = "Geeks", index = 0, ch = 'g'
Output: "geeks"
```

**方法 1:使用字符串类**

到目前为止，[字符串](https://www.geeksforgeeks.org/string-class-in-java/)类中没有预定义的方法来替换字符串中的特定字符。但是，这可以通过用两个不同的子字符串构造一个新的字符串来间接实现，一个从开始到特定索引–1，新字符在特定索引处，另一个从索引+ 1 到结束。
以下是上述办法的实施情况:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
public class GFG {

    public static void main(String args[])
    {

        // Get the String
        String str = "Geeks Gor Geeks";

        // Get the index
        int index = 6;

        // Get the character
        char ch = 'F';

        // Print the original string
        System.out.println("Original String = " + str);

        str = str.substring(0, index) + ch
              + str.substring(index + 1);

        // Print the modified string
        System.out.println("Modified String = " + str);
    }
}
```

**Output**

```java
Original String = Geeks Gor Geeks
Modified String = Geeks For Geeks
```

**方法二:使用 StringBuilder**

与字符串类不同，[字符串构建器](https://www.geeksforgeeks.org/stringbuilder-class-in-java-with-examples/)类为此有一个预定义的方法——setCharAt()。通过调用此方法并将字符和索引作为参数传递，替换特定索引处的字符。
以下是上述办法的实施情况:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
public class GFG {

    public static void main(String args[])
    {

        // Get the String
        String str = "Geeks Gor Geeks";

        // Get the index
        int index = 6;

        // Get the character
        char ch = 'F';

        // Print the original string
        System.out.println("Original String = " + str);

        StringBuilder string = new StringBuilder(str);
        string.setCharAt(index, ch);

        // Print the modified string
        System.out.println("Modified String = " + string);
    }
}
```

**Output**

```java
Original String = Geeks Gor Geeks
Modified String = Geeks For Geeks
```

**方法三:使用 StringBuffer**

像 StringBuilder 一样， [StringBuffer](https://www.geeksforgeeks.org/stringbuffer-class-in-java/) 类为此有一个预定义的方法——setCharAt()。通过调用此方法并将字符和索引作为参数传递，替换特定索引处的字符。StringBuffer 是*线程安全*。与 StringBuffer 相比，StringBuilder 更快，但不是线程安全的。

以下是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
public class GFG {

    public static void main(String args[])
    {

        // Get the String
        String str = "Geeks Gor Geeks";

        // Get the index
        int index = 6;

        // Get the character
        char ch = 'F';

        // Print the original string
        System.out.println("Original String = " + str);

        StringBuffer string = new StringBuffer(str);
        string.setCharAt(index, ch);

        // Print the modified string
        System.out.println("Modified String = " + string);
    }
}
```

**Output**

```java
Original String = Geeks Gor Geeks
Modified String = Geeks For Geeks
```