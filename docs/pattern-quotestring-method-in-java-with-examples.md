# Java 中的模式引用(字符串)方法，示例

> 原文:[https://www . geesforgeks . org/pattern-quote string-method-in-Java-with-examples/](https://www.geeksforgeeks.org/pattern-quotestring-method-in-java-with-examples/)

**引用一个**模式**类的(字符串)**方法，用于返回作为参数传递给方法的指定字符串的文字模式字符串。此方法生成一个等效于的字符串，可用于创建模式。输入序列中的元字符或转义序列不会被赋予特殊含义。如果您编译由引号方法返回的值，您将得到一个与您作为参数传递给方法的文字字符串相匹配的模式。\Q 和\E 标记字符串引用部分的开始和结束。

**语法:**

```
public static String quote(String s)

```

**参数:**该方法接受单个参数 **s** ，表示要直译的字符串。

**返回值:**该方法返回字符串 s 的文字字符串替换

以下程序举例说明了报价()方法:
**程序 1:**

```
// Java program to demonstrate
// Pattern.quote() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a REGEX String
        String REGEX = "ee";

        // create the string
        // in which you want to search
        String actualString
            = "geeksforgeeks";

        // create equivalent String for REGEX
        String eqREGEX = Pattern.quote(REGEX);

        // create a Pattern using eqREGEX
        Pattern pattern = Pattern.compile(eqREGEX);

        // get a matcher object
        Matcher matcher = pattern.matcher(actualString);

        // print values if match found
        boolean matchfound = false;
        while (matcher.find()) {
            System.out.println("found the Regex in text:"
                               + matcher.group()
                               + " starting index:"
                               + matcher.start()
                               + " and ending index:"
                               + matcher.end());

            matchfound = true;
        }
        if (!matchfound) {
            System.out.println("No match found for Regex.");
        }
    }
}
```

**Output:**

```
found the Regex in text:ee starting index:1 and ending index:3
found the Regex in text:ee starting index:9 and ending index:11

```

**程序 2:**

```
// Java program to demonstrate
// Pattern.quote() method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a REGEX String
        String REGEX = "welcome";

        // create the string
        // in which you want to search
        String actualString
            = "welcome to jungle";

        // create equivalent String for REGEX
        String eqREGEX = Pattern.quote(REGEX);

        // create a Pattern using eqREGEX
        Pattern pattern = Pattern.compile(eqREGEX);

        // get a matcher object
        Matcher matcher = pattern.matcher(actualString);

        // print values if match found
        boolean matchfound = false;
        while (matcher.find()) {
            System.out.println("match found");
            matchfound = true;
        }
        if (!matchfound) {
            System.out.println("No match found");
        }
    }
}
```

**Output:**

```
match found

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/regex/pattern . html # quote(Java . lang . string)](https://docs.oracle.com/javase/10/docs/api/java/util/regex/Pattern.html#quote(java.lang.String))