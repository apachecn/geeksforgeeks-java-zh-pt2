# Java 中的 StringTokenizer 方法，带示例|第 2 集

> 原文:[https://www . geeksforgeeks . org/stringtokenizer-methods-Java-examples-set-2/](https://www.geeksforgeeks.org/stringtokenizer-methods-java-examples-set-2/)

[Java 中的 StringTokenizer 类](https://www.geeksforgeeks.org/stringtokenizer-class-java-example-set-1-constructors/)用于将一个字符串分解成令牌。必须通过 [StringTokenzier 类](https://www.geeksforgeeks.org/stringtokenizer-class-java-example-set-1-constructors/)来讨论概念和构造函数，这有助于更好地理解下面讨论的方法:

**StringTokenizer 类的方法如下:**

*   hasmoretokens
*   下一个令牌
*   计数令牌
*   下一个元素
*   hasmoreelements

**方法 1:** hasMoreTokens()

该方法在测试 StringTokenizer 的字符串是否存在标记时发挥作用。那些被 StringTokenizer 对象视为分隔符的字符将被更改为字符串分隔符中的字符。然后返回字符串中当前位置的下一个标记。

**语法:**

```
public boolean hasMoreTokens()
```

**返回类型:**布尔值，当且仅当字符串中当前位置的下一个标记存在时为真，否则为假。

**方法 2:** nextToken()

方法从给定的 StringTokenizer 返回下一个标记。

**语法:**

```
public String nextToken()
```

**返回类型:**给定字符串生成器的下一个令牌(如果存在)。

**异常抛出:**T2【nosucheelementexception】如果没有剩余代币的话。

**方法 3:count token()**

该方法返回存在的令牌总数，以便我们可以在它给出异常之前使用 nextToken()方法。

**语法:**

```
public int countTokens()
```

**返回类型:**使用当前分隔符集的字符串中剩余的标记数。

**示例**

## Java

```
// Java Program to Illustrate Methods of StringTokenizer class
// Via hasMoreToken(), nextToken() and countTokens()

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[]) {

        // Input strings
        String mydelim = " : ";
        String mystr = "JAVA : Code : String : Tokenizer : Geeks";

        // Use of Constructor 2
        // Here we are passing Delimiter - "mydelim"
        StringTokenizer geeks3 =
            new StringTokenizer(mystr, mydelim);

        // Printing count of tokens and tokens
        // using countTokens() method
        int count = geeks3.countTokens();
        System.out.println("Number of tokens : " + count + "\n");

        // Iterating to get the tokens
        for (int i = 0; i < count; i++)
            System.out.println("token at [" + i + "] : "
                               + geeks3.nextToken());

        // checks for more tokens using hasMoreTokens() method
        // which holds true til there is single element remaining
        while (geeks3.hasMoreTokens())

            // Returning the next token
            // using nextToken() method
            System.out.println(geeks3.nextToken());
    }
}
```

**输出**

```
Number of tokens : 5

token at [0] : JAVA
token at [1] : Code
token at [2] : String
token at [3] : Tokenizer
token at [4] : Geeks
```

**方法 4:** nextElement()

该方法的工作方式类似于 nextToken，只是它返回的是一个对象而不是字符串。存在，以便此类可以实现枚举接口。

**语法:**

```
public Object nextElement()
```

**返回类型:**给定字符串生成器的下一个令牌。

**异常抛出:**[no suchelementexception](https://www.geeksforgeeks.org/how-to-fix-java-util-nosuchelementexception-in-java/)如果没有剩余代币。

**方法 5:**hasmorelements()

此方法返回的值与 hasMoreToken 相同。它的存在是为了让类可以实现枚举接口。

**语法:**

```
public boolean hasMoreElements()
```

**返回类型:**布尔值，如果字符串中存在标记，则为真，否则为假

**示例**

## Java

```
// Java Program to Illustrate Methods of StringTokenizer
// Class Via hasMoreElements, nextElement and nextElement

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Input strings
        String mydelim = " : ";
        String mystr
            = "JAVA : Code : String : Tokenizer : Geeks";

        // Use of Constructor 2
        // Here we are passing Delimiter - "mydelim"
        StringTokenizer geeks
            = new StringTokenizer(mystr, mydelim);

        // Counting no. of tokens present
        // using countTokens() method
        int count = geeks.countTokens();

        // Printing no. of tokens present
        System.out.println("Number of tokens : " + count);

        //  Condition holds true till there is
        // single token remaining using hasMoreElements()
        // method True if tokens are present
        while (geeks.hasMoreElements())

            //  Returning the next token
            // using nextElement() method
            System.out.println(geeks.nextElement());
    }
}
```

**Output**

```
Number of tokens : 5
JAVA
Code
String
Tokenizer
Geeks
```

> **提示:**一定要记住所列的某些要点:
> 
> *   The count token () method is a good alternative to the combination of *hasmoretoken ()* and *next token ()* .
> *   If you are also interested in the number of tokens, use the combination of *counttoken ()* and *next token ()* .

本文由**莫希特·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。