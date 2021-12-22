# 在 Java 中交换字符串中的成对字符

> 原文:[https://www . geesforgeks . org/交换-java 字符串中的字符对/](https://www.geeksforgeeks.org/swapping-pairs-of-characters-in-a-string-in-java/)

给定字符串 **str** ，任务是编写一个 Java 程序来交换字符串的成对字符。如果字符串包含奇数个字符，则最后一个字符保持不变。

**示例:**

> **输入:** str = "Java "
> 
> ◆T0 输出：
> 
> **说明:**给定的字符串包含偶数个字符。因此，我们交换每一对字符。
> 
> **输入:** str = "GeeksForGeeks "
> 
> **输出:**蛋奶器
> 
> **说明:**给定字符串包含奇数个字符。因此，我们交换每对字符，最后一个字符保持原样。

**1。使用** [**弦**](https://www.geeksforgeeks.org/java-string-tochararray-example/) **法**

1.  获取字符串以交换一对字符。
2.  检查字符串是否为空，然后返回字符串。
3.  将给定字符串转换为字符数组。
4.  遍历字符数组并交换字符。
5.  现在，打印结果。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to swap pair
// of characters of a string

class GFG {

    // Function to swap pair of
    // characters of a string
    public static String swapPair(String str)
    {

        // Checking if string is null
        // or empty then return str
        if (str == null || str.isEmpty())
            return str;

        // Converting the given string
        // into a character array
        char[] ch = str.toCharArray();

        // Traverse the character array
        for (int i = 0; i < ch.length - 1; i += 2) {

            // Swapping the characters
            char temp = ch[i];
            ch[i] = ch[i + 1];
            ch[i + 1] = temp;
        }

        // Converting the result into a
        // string and return
        return new String(ch);
    }

    // Driver Code
    public static void main(String args[])
    {

        // Given String str
        String str = "GeeksForGeeks";

        // Print the result
        System.out.println(swapPair(str));
    }
}
```

**Output**

```
eGkeFsroeGkes

```

**2。使用**[**stringbuffer . append()**](https://www.geeksforgeeks.org/stringbuffer-append-method-in-java-with-examples/)**方法**

1.  获取字符串以交换一对字符。
2.  检查字符串是否为空，然后返回字符串。
3.  用作为参数传递的字符串长度创建一个 *StringBuffer* 对象。
4.  遍历字符串，并以相反的顺序追加 *StringBuffer* 对象中的字符。
5.  检查字符串是否包含奇数个字符，然后将最后一个字符追加到 *StringBuffer* 对象中。
6.  现在，打印结果。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to swap pair
// of characters of a string

class GFG {

    // Function to swap pair of
    // characters of a string
    public static String swapPairs(String str)
    {

        // Checking if string is null
        // or empty then return str
        if (str == null || str.isEmpty())
            return str;

        int len = str.length();

        // Creating a StringBuffer object with
        // length of the string passed as a parameter
        StringBuffer sb = new StringBuffer(len);

        // Traverse the string and append
        // the character in the StringBuffer
        // object in reverse order
        for (int i = 0; i < len - 1; i += 2) {
            sb.append(str.charAt(i + 1));
            sb.append(str.charAt(i));
        }

        // Checking if the string has
        // odd number of characters
        // then append the last character
        // into StringBuffer object
        if (len % 2 != 0) {
            sb.append(str.charAt(len - 1));
        }

        // Converting the StringBuffer
        // into the string and return
        return sb.toString();
    }

    // Driver Code
    public static void main(String args[])
    {

        // Given String str
        String str = "GeeksForGeeks";

        // Print the result
        System.out.println(swapPairs(str));
    }
}
```

**Output**

```
eGkeFsroeGkes

```