# Java 中的 StringJoiner merge()方法

> 原文:[https://www . geesforgeks . org/string joiner-merge-method-in-Java/](https://www.geeksforgeeks.org/stringjoiner-merge-method-in-java/)

[StringJoiner](https://www.geeksforgeeks.org/java-util-stringjoiner-java8/) 的**合并(StringJoiner other)** 将没有前缀和后缀的给定 StringJoiner 的内容添加为下一个元素(如果它是非空的)。如果给定的 StringJoiner 为空，则调用无效。
**语法:**

```
public StringJoiner merge(StringJoiner other)
```

**参数:**此方法接受一个强制参数 **other** ，它是其内容应该合并到此参数中的 StringJoiner
**返回:**此方法返回此 StringJoiner
**异常:**此方法抛出 **NullPointerException** 如果另一个 StringJoiner 为空
下面的程序说明了 merge()方法:
**示例 1:** 演示带有分隔符“的 merge()

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// merge() method of StringJoiner

import java.util.StringJoiner;

public class GFG {
    public static void main(String[] args)
    {

        // Creating StringJoiner with delimiter " "
        StringJoiner str1 = new StringJoiner(" ");

        // Adding elements in the StringJoiner
        str1.add("Geeks");
        str1.add("for");
        str1.add("Geeks");

        // Print the StringJoiner
        System.out.println("StringJoiner 1: "
                           + str1.toString());

        // Creating the second StringJoiner
        StringJoiner str2 = new StringJoiner(" ");

        str2.add("A");
        str2.add("Computer");
        str2.add("Portal");

        // Print the second StringJoiner
        System.out.println("StringJoiner 2: "
                           + str2.toString());

        // Merging the StringJoiner using merge()
        StringJoiner str = str1.merge(str2);

        // Printing the merged StringJoiner
        System.out.println("Merged StringJoiner : "
                           + str);
    }
}
```

**Output:** 

```
StringJoiner 1: Geeks for Geeks
StringJoiner 2: A Computer Portal
Merged StringJoiner : Geeks for Geeks A Computer Portal
```

**示例 2:** 演示带分隔符“、”
的 merge()

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// merge() method of StringJoiner

import java.util.StringJoiner;

public class GFG1 {
    public static void main(String[] args)
    {

        // Creating StringJoiner with delimiter ", "
        StringJoiner str1 = new StringJoiner(", ");

        // Adding elements in the StringJoiner
        str1.add("Geeks");
        str1.add("for");
        str1.add("Geeks");

        // Print the StringJoiner
        System.out.println("StringJoiner 1: "
                           + str1.toString());

        // Creating the second StringJoiner
        StringJoiner str2 = new StringJoiner(", ");

        str2.add("A");
        str2.add("Computer");
        str2.add("Portal");

        // Print the StringJoiner
        System.out.println("StringJoiner 2: "
                           + str2.toString());

        // Merging the StringJoiner using merge()
        StringJoiner str = str1.merge(str2);

        // Printing the merged StringJoiner
        System.out.println("Merged StringJoiner : "
                           + str);
    }
}
```

**Output:** 

```
StringJoiner 1: Geeks, for, Geeks
StringJoiner 2: A, Computer, Portal
Merged StringJoiner : Geeks, for, Geeks, A, Computer, Portal
```

**示例 3:** 演示空指针异常

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// merge() method of StringJoiner

import java.util.StringJoiner;

public class GFG1 {
    public static void main(String[] args)
    {

        // Creating StringJoiner with delimiter ", "
        StringJoiner str1 = new StringJoiner(", ");

        // Adding elements in the StringJoiner
        str1.add("Geeks");
        str1.add("for");
        str1.add("Geeks");

        // Print the StringJoiner
        System.out.println("StringJoiner 1: "
                           + str1.toString());

        // Creating the second StringJoiner
        // to be merged as null
        StringJoiner str2 = null;

        // Print the StringJoiner
        System.out.println("StringJoiner 2: "
                           + str2);

        try {

            // Merging the StringJoiner using merge()
            StringJoiner str = str1.merge(str2);
        }
        catch (Exception e) {
            System.out.println("Exception during merge: "
                               + e);
        }
    }
}
```

**Output:** 

```
StringJoiner 1: Geeks, for, Geeks
StringJoiner 2: null
Exception during merge: java.lang.NullPointerException
```