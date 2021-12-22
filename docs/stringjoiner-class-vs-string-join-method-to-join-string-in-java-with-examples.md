# StringJoiner 类 vs . String . Join()Java 中连接字符串的方法，示例

> 原文:[https://www . geesforgeks . org/string joiner-class-vs-string-join-method-to-join-string-in-Java-with-examples/](https://www.geeksforgeeks.org/stringjoiner-class-vs-string-join-method-to-join-string-in-java-with-examples/)

在 Java 8 之前，当我们需要连接一组字符串时，我们需要手动编写代码。除此之外，我们需要重复使用分隔符，有时这会导致几个错误。但是在 Java 8 之后，我们可以使用 StringJoiner 类和 String.join()方法连接字符串，这样我们就可以轻松实现我们的目标。

**示例:不带 StringJoiner 类，不带 String.join()方法**

**方法:**

*   In this program, we will not use java 8\. We will try to operate manually and try to understand how much code/steps we need to achieve our goal for this simple operation of string concatenation with delimiters.
*   First, we will connect three strings "DSA", "FAANG" and "ALGO", and the separator will be "gfg". For this reason, we need to write the separator before adding the next string every time.
*   Next, we will join the elements of the array list containing the strings DSA, FAANG and ALGO, and the separator will be gfg. To do this, we need to traverse the array list and then add the strings with the separator.
*   Note here that for i=0, we directly assign the string joined2 to the first element of ArrayList, because if we don't put this condition in, we will get the output "gfg DSA gfg FAANG gfg ALGO", and the actual output has no separator before the first element of ArrayList "DSA gfg FAANG gfg ALGO".
*   From the code, we can see how much code has been written to complete this simple task. Now we will use the StringJoiner class and the String.join () method to complete this task.

## Java

```
// Java program for joining the strings before Java8
// by simple method using '+' to concatenate 

import java.io.*;
import java.util.ArrayList;
import java.util.Arrays;

class GFG {
    public static void main(String[] args)
    {
        // Here we need to join strings "DSA","FAANG","ALGO"
        // and with delimiter " gfg "
        String joined = "DSA"
                        + " gfg "
                        + "FAANG"
                        + " gfg "
                        + "ALGO";

        // Here we created an ArrayList of strings
        // ArrayList contains "DSA","FAANG","ALGO"
        ArrayList<String> gfgstrings = new ArrayList<>(
            Arrays.asList("DSA", "FAANG", "ALGO"));

        String joined2 = "";

        // Now we will iterate over ArrayList
        for (int i = 0; i < gfgstrings.size(); i++) {

            // for i== 0 we do not want to add space before
            // first word thats why we checked for i=0
            if (i == 0) {
                joined2 = gfgstrings.get(i);
            }

            else {
                joined2
                    = joined2 + " gfg " + gfgstrings.get(i);
            }
        }

        // printing the first output
        System.out.println(joined);
        System.out.println("--------------------");

        // printing the second output
        System.out.println(joined2);
    }
}
```

**输出**

```
DSA gfg FAANG gfg ALGO
--------------------
DSA gfg FAANG gfg ALGO
```