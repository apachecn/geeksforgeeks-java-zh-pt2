# 在 Java 中交换字符串的字符

> 原文:[https://www . geesforgeks . org/swapping-characters-string-Java/](https://www.geeksforgeeks.org/swapping-characters-string-java/)

正如我们所知，Java 中[字符串的对象是不可变的(也就是说，一旦它被创建，我们就不能执行任何更改)。](https://www.geeksforgeeks.org/string-class-in-java/)

为了对存储在 string 对象中的字符串进行修改，我们将其复制到一个字符数组、StringBuffer 等，并对复制对象进行修改。

在本文中，我们将通过一些方法来交换给定字符串的字符，并获得一个新字符串(带有交换的字符)，而原始字符串不受影响。

通过下面的例子让我们看到一些方法，通过这些方法我们可以交换字符并生成新的字符串
例子:
**方法 1(使用 toCharArray)**
在这个方法中，我们将字符串转换成字符数组并执行所需的交换。

```
// Java program to demonstrate character swap
// using toCharArray().
public class GFG {
    static char[] swap(String str, int i, int j)
    {
        char ch[] = str.toCharArray();
        char temp = ch[i];
        ch[i] = ch[j];
        ch[j] = temp;
        return ch;
    }

    public static void main(String args[])
    {
        String s = "geeksforgeeks";

        System.out.println(swap(s, 6, s.length() - 2));
        System.out.println(swap(s, 0, s.length() - 1));

        System.out.println(s);
    }
}
```

**Output:**

```
geeksfkrgeeos
seeksforgeekg
geeksforgeeks

```

**方法 2(使用 subString())**
我们使用给定字符串的子字符串构建修改后的字符串。

```
// Java program to demonstrate character swap
// using subString()

public class GFG {
    static String swap(String str, int i, int j)
    {
        if (j == str.length() - 1)
            return str.substring(0, i) + str.charAt(j)
                + str.substring(i + 1, j) + str.charAt(i);

        return str.substring(0, i) + str.charAt(j)
            + str.substring(i + 1, j) + str.charAt(i)
            + str.substring(j + 1, str.length());
    }

    public static void main(String args[])
    {
        String s = "geeksforgeeks";

        System.out.println(swap(s, 6, s.length() - 2));
        System.out.println(swap(s, 0, s.length() - 1));

        // Original String doesn't change
        System.out.println(s);
    }
}
```

**Output:**

```
geeksfkrgeeos
seeksforgeekg
geeksforgeeks

```

**方法 3(使用 StringBuilder 或 StringBuffer)**
在这个方法中，你可以根据情况使用 StringBuilder 或 StringBuffer。参见 Java 中的[String vs StringBuilder vs StringBuffer 来决定何时使用哪一个。](https://www.geeksforgeeks.org/g-fact-27-string-vs-stringbuilder-vs-stringbuffer/)

```
// Java program to demonstrate character swap
// using StringBuilder

public class GFG {
    static String swap(String str, int i, int j)
    {
        StringBuilder sb = new StringBuilder(str);
        sb.setCharAt(i, str.charAt(j));
        sb.setCharAt(j, str.charAt(i));
        return sb.toString();
    }

    public static void main(String args[])
    {
        String s = "geeksforgeeks";

        System.out.println(swap(s, 6, s.length() - 2));
        System.out.println(swap(s, 0, s.length() - 1));

        // Original String doesn't change
        System.out.println(s);
    }
}
```

**Output:**

```
geeksfkrgeeos
seeksforgeekg
geeksforgeeks

```

输出:

```
geeksfkrgeeos
seeksforgeekg
geeksforgeeks

```

本文由 **Sumit Ghosh** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。