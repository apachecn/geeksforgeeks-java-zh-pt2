# Splitter fixedLength()方法|番石榴|爪哇

> 原文:[https://www . geesforgeks . org/splitter-fixed length-method-guava-Java/](https://www.geeksforgeeks.org/splitter-fixedlength-method-guava-java/)

方法 **fixedLength(int length)** 返回一个拆分器，将字符串分成给定长度的片段。例如， **Splitter.fixedLength(2)。split("abcde")** 返回一个包含 **["ab "、" cd "、" e"]** 的可迭代表。最后一块可以小于长度，但永远不会是空的。

**语法:**

```
public static Splitter fixedLength(int length)

```

**参数:**该方法以*长度*为参数，即分割后所需的片长。它是正整数值。

**返回值:**这个方法返回一个拆分器，默认设置，可以拆分成固定大小的块。

**异常:**如果长度为零或负数，此方法抛出***IllegalArgumentException***。

**例 1:**

```
// Java code to show implementation of
// fixedLength(int length) method
// of Guava's Splitter Class

import com.google.common.base.Splitter;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a string variable
        String str = "Delhi Noida Chandigarh";

        // Initially setting length as 3
        System.out.println("When Length is 3 : ");

        // Using fixedLength(int length) method which
        // returns a splitter that divides strings
        // into pieces of the given length
        Iterable<String> result = Splitter.fixedLength(3)
                                      .trimResults()
                                      .split(str);

        for (String temp : result) {
            System.out.println(temp);
        }

        // Setting length as 4
        System.out.println("\n\nWhen Length is 4 : ");

        // Using fixedLength(int length) method which
        // returns a splitter that divides strings
        // into pieces of the given length
        Iterable<String> result1 = Splitter.fixedLength(4)
                                       .trimResults()
                                       .split(str);

        for (String temp : result1) {
            System.out.println(temp);
        }
    }
}
```

**Output:**

```
When Length is 3 : 
Del
hi
Noi
da
Cha
ndi
gar
h

When Length is 4 : 
Delh
i No
ida
Chan
diga
rh

```

**示例 2:** 显示 IllegalArgumentException

```
// Java code to show implementation of
// fixedLength(int length) method
// of Guava's Splitter Class

import com.google.common.base.Splitter;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        try {
            // Creating a string variable
            String str = "GeeksforGeeks is best";

            // Initially setting length as 0
            // This should throw "IllegalArgumentException"
            // as length is 0
            System.out.println("When Length is 0 : ");

            // Using fixedLength(int length) method which
            // returns a splitter that divides strings
            // into pieces of the given length
            Iterable<String> result = Splitter.fixedLength(0)
                                          .trimResults()
                                          .split(str);

            for (String temp : result) {
                System.out.println(temp);
            }
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```
When Length is 0 : 
Exception: java.lang.IllegalArgumentException: 
           The length may not be less than 1

```