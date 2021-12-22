# Java 中的模式拆分(CharSequence，int)方法，示例

> 原文:[https://www . geesforgeks . org/pattern-splitcharsequenceint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/pattern-splitcharsequenceint-method-in-java-with-examples/)

**一个**模式**类的 split(CharSequence，int)** 方法，用于分割作为参数传递给该模式匹配项周围的方法的给定 char 序列。返回的数组包含由该方法创建的输入序列的每个子字符串。数组中的子字符串按照它们在输入中出现的顺序排列。如果这个模式不匹配输入的任何子序列，那么得到的数组只有一个元素，即字符串形式的输入序列。作为 int 传递的 limit 参数有助于计算应用模式的次数，并影响结果数组的长度。如果极限 n 大于零，则该模式最多应用 n-1 次。如果 n 为非正或零，则该模式将被应用尽可能多的次数。

**语法:**

```java
public String[] split?(CharSequence input, int limit)

```

**参数:**该方法接受两个参数一个**输入**代表待拆分字符序列，另一个**限制**代表描述中提到的结果阈值。

**返回值:**该方法返回字符串数组，该数组是通过围绕该模式的匹配项拆分输入来计算的。

下面的程序说明了分割(CharSequence，int)方法:

**程序 1:**

```java
// Java program to demonstrate
// Pattern.split(CharSequence) method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a REGEX String
        String REGEX = "geeks";

        // create the string
        // in which you want to search
        String actualString
            = "Welcome to geeks for geeks";

        // create a Pattern using REGEX
        Pattern pattern = Pattern.compile(REGEX);

        // create limit to 2
        // so it can applied at most limit - 1 time
        int limit = 2;

        // split the text
        String[] array
            = pattern.split(actualString, limit);

        // print array
        for (int i = 0; i < array.length; i++) {
            System.out.println("array[" + i
                               + "]=" + array[i]);
        }
    }
}
```

**输出:**

```java
array[0]=Welcome to 
array[1]= for geeks

```

**程序二:**

```java
// Java program to demonstrate
// Pattern.split(CharSequence) method

import java.util.regex.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a REGEX String
        String REGEX = "ee";

        // create the string
        // in which you want to search
        String actualString
            = "aaeebbeecceeddee";

        // create a Pattern using REGEX
        Pattern pattern = Pattern.compile(REGEX);

        // create limit to 2
        // so it can applied at most limit - 1 time
        int limit = 0;

        // split the text
        String[] array
            = pattern.split(actualString, limit);

        // print array
        for (int i = 0; i < array.length; i++) {
            System.out.println("array[" + i
                               + "]=" + array[i]);
        }
    }
}
```

**输出:**

```java
array[0]=aa
array[1]=bb
array[2]=cc
array[3]=dd

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/regex/pattern . html # split(Java . lang . charsequence，int)](https://docs.oracle.com/javase/10/docs/api/java/util/regex/Pattern.html#split(java.lang.CharSequence, int))