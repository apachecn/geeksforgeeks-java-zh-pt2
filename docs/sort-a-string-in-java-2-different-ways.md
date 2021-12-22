# 用 Java 对字符串进行排序(两种不同的方式)

> 原文:[https://www . geesforgeks . org/sort-a-string-in-Java-2-differential-way/](https://www.geeksforgeeks.org/sort-a-string-in-java-2-different-ways/)

String 类没有任何直接对字符串进行排序的方法，但是我们可以通过一个接一个地应用其他方法来对字符串进行排序。字符串是一个字符序列。在 java 中，String 的对象是不可变的，这意味着一个常量，一旦创建就不能更改。

**创建字符串**

用 Java 创建字符串有两种方法:

*   ***字符串文字***

```java
String s = “GeeksforGeeks”;
```

*   **使用** ***新增*** **关键词**

```java
String s = new String (“GeeksforGeeks”);
```

> **注意:**我们知道在 java 中 String 是[不可变的](https://www.geeksforgeeks.org/how-to-initialize-and-compare-strings-in-java/)，因此在第三步中我们必须创建一个新的字符串。

**方法:**

有两种方法可以让我们按照字母顺序对 java 中的任何字符串进行排序

1.  不使用 sort()方法
2.  用*排序()方法*

插图:

```java
Input string : "geeksforgeeks"
Output string : "eeeefggkkorss"
```

现在让我们讨论方法并实现它们。

**方法 1:** 不使用 sort()方法

在这里，我们将设置一种方法，在不使用任何预定义逻辑的情况下对字符串进行排序。因此，从面试的角度来看，这也成为一种重要的方法。

**程序:**

1.  借助 string 类的 toCharArray()方法将字符串转换为数组
2.  现在使用嵌套循环来检查数组元素的交换。
3.  打印这些字符数组元素。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Sort a String Alphabetically
// Using toCharArray() method
// Without using sort() method

// Importing required classes
import java.io.*;
import java.util.Arrays;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args) throws Exception
    {
        // Custom string input
        String str = "geeksforgeeks";

        // Converting string into an array for computation
        char arr[] = str.toCharArray();

        // Nested loops for comparison of characters
        // in above character array

        char temp;

        int i = 0;
        while (i <= arr.length) {
            int j = i + 1;
            while (j <= arr.length) {
                if (arr[j] < arr[i]) {

                    // Comparing the characters one by one
                    temp = arr[i];
                    arr[i] = arr[j];
                    arr[j] = temp;
                }
                j += 1;
            }
            i += 1;
        }

        // By now loop is done means we have
        // iterated the whole array
        System.out.println(arr);
    }
}
```

**输出:**

```java
eeeefggkkorss
```

**方法 2:** 配合使用*排序()方法*

**2A** 同使用*排序()方法-* 自然排序

**程序:**

1.  主要逻辑是将 String 类的 [*toCharArray()方法*](https://www.geeksforgeeks.org/java-string-tochararray-example/) 置于输入字符串之上，为输入字符串创建一个字符数组。
2.  现在使用*[*arrays . sort(char c[])*](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/)方法对字符数组进行排序。*
3.  *使用字符串类构造函数从字符数组创建排序字符串。*

***例 1***

## *Java 语言(一种计算机语言，尤用于创建网站)*

```java
*// Java program to Sort a String Alphabetically
// Using toCharArray() method
// With using the sort() method

// Importing Arrays class from java.util package
import java.util.Arrays;

// Main class
public class GFG {
    // Method 1
    // To sort a string alphabetically
    public static String sortString(String inputString)
    {
        // Converting input string to character array
        char tempArray[] = inputString.toCharArray();

        // Sorting temp array using
        Arrays.sort(tempArray);

        // Returning new sorted string
        return new String(tempArray);
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Custom string as input
        String inputString = "geeksforgeeks";
        String outputString = sortString(inputString);

        // Print and display commands

        // Input string
        System.out.println("Input String : " + inputString);
        // Output string
        System.out.println("Output String : "
                           + outputString);
    }
}*
```

***Output**

```java
Input String : geeksforgeeks
Output String : eeeefggkkorss
```* 

***2B** 同使用*排序()方法-* 自定义排序*

> *[*arrays . sort(char c[])*](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/)方法根据字符的 ASCII 值对其进行排序，我们可以定义自定义的[比较器](https://www.geeksforgeeks.org/comparator-interface-java/)对字符串进行排序。*

*插图:*

```java
*Input String : GeeksforGeeks
Output String : eeeefGGkkorss*
```

***程序:***

1.  *将输入字符串转换为[字符](https://www.geeksforgeeks.org/character-class-java/)数组。没有直接的方法去做。我们将使用 for 循环来填充数组。*
2.  *使用 [*Arrays.sort(T [ ]，Comparator c)*](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/) 方法对字符数组进行排序。为此，我们必须基于我们的自定义排序行为来实现 [*compare()*](https://www.geeksforgeeks.org/comparator-interface-java/) 方法。*
3.  *现在我们可以使用字符串生成器将字符数组转换为字符串。*

***例 2***

## *Java 语言(一种计算机语言，尤用于创建网站)*

```java
*// Java Program to Sort a Mixed String Containing
// Uppercase and Lowercase Characters

// Importing required classes
import java.util.Arrays;
import java.util.Comparator;

// Main class
class GFG {
    // Method 1
    // To sort a mixed string
    public static String sortString(String inputString)
    {
        // Converting input string to Character array
        Character tempArray[]
            = new Character[inputString.length()];

        for (int i = 0; i < inputString.length(); i++) {
            tempArray[i] = inputString.charAt(i);
        }

        // Sort, ignoring case during sorting
        Arrays.sort(tempArray, new Comparator<Character>() {

          // Method 2
            // To compare characters
            @Override
            public int compare(Character c1, Character c2)
            {
                // Ignoring case
                return Character.compare(
                    Character.toLowerCase(c1),
                    Character.toLowerCase(c2));
            }
        });

        // Using StringBuilder to convert Character array to
        // String
        StringBuilder sb
            = new StringBuilder(tempArray.length);

        for (Character c : tempArray)
            sb.append(c.charValue());

        return sb.toString();
    }

    // Method 3
    // MAin driver method
    public static void main(String[] args)
    {
        // Custom input string
        String inputString = "GeeksforGeeks";

        // Calling method 1 to sort input string
        // and storing in a string
        String outputString = sortString(inputString);

        // Print and display the input and output strings
        System.out.println("Input String : " + inputString);
        System.out.println("Output String : "
                           + outputString);
    }
}*
```

***Output**

```java
Input String : GeeksforGeeks
Output String : eeeefGGkkorss
```* 

> ***注:***
> 
> ```java
> *public int compare(Object o1, Object o2) {}*
> ```
> 
> *   *如果 o1 必须在 o2 之前到来，则必须返回-ve*
> *   *如果 o1 必须在 o2 之后，则必须返回+ve*
> *   *如果 o1 等于 o2，则必须返回 0*

*本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。*