# Java 中的模式匹配器(CharSequence)方法，示例

> 原文:[https://www . geeksforgeeks . org/pattern-matchercharsequence-method-in-Java-with-examples/](https://www.geeksforgeeks.org/pattern-matchercharsequence-method-in-java-with-examples/)

**模式**类的**匹配器(CharSequence)** 方法用于生成匹配器，该匹配器有助于将给定的输入作为参数与该模式的方法进行匹配。当我们需要一次对照文本检查一个模式时，Pattern.matches()方法非常有用，并且 Pattern 类的默认设置是合适的。

**语法:**

```
public Matcher matcher(CharSequence input)

```

**参数:**该方法接受单个参数**输入**，代表要匹配的字符序列。

**返回值:**这个方法为这个模式返回一个新的匹配器。

下面的程序说明了匹配器(CharSequence)方法:

**程序 1:**

```
// Java program to demonstrate
// Pattern.matcher(CharSequence) method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a REGEX String
        String REGEX = "(.*)(ee)(.*)?";

        // create the string
        // in which you want to search
        String actualString
            = "geeksforgeeks";

        // create a Pattern
        Pattern pattern = Pattern.compile(REGEX);

        // get a matcher object
        Matcher matcher = pattern.matcher(actualString);

        // print values if match found
        boolean matchfound = false;
        while (matcher.find()) {
            System.out.println("found the Regex in text:"
                               + matcher.group()
                               + " starting index:" + matcher.start()
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
found the Regex in text:geeksforgeeks starting index:0 and ending index:13

```

**程序 2:**

```
// Java program to demonstrate
// Pattern.matcher(CharSequence) method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a REGEX String
        String REGEX = "(.*)(welcome)(.*)?";

        // create the string
        // in which you want to search
        String actualString
            = "geeksforgeeks";

        // create a Pattern
        Pattern pattern = Pattern.compile(REGEX);

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
No match found

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/util/regex/pattern . html # matcher(Java . lang . charsequence)](https://docs.oracle.com/javase/10/docs/api/java/util/regex/Pattern.html#matcher(java.lang.CharSequence))