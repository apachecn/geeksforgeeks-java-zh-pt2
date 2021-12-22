# 【splitToList()方法|番石榴| Java

> 原文:[https://www . geesforgeks . org/splitter-splittolist-method-guava-Java/](https://www.geeksforgeeks.org/splitter-splittolist-method-guava-java/)

方法**splitToList(CharSequence sequence)**将序列拆分成字符串组件，并将其作为不可变列表返回。

**语法:**

```java
public List<String> 
    splitToList(CharSequence sequence)

```

**参数:**该方法以*序列*为参数，即待拆分的字符序列。

**返回值:**这个方法返回一个从参数中分割出来的不可变的段列表。

以下示例说明了 splitToList()方法的工作原理:

**例 1:**

```java
// Java code to show implementation of
// splitToList method
// of Guava's Splitter Class

import com.google.common.base.Splitter;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a string variable
        String str = "Hello, geeks, for, geeks, noida";

        // SplitToList returns a List of the strings.
        // This can be transformed to an ArrayList
        // or used directly in a loop.
        List<String> myList = Splitter.on(',').splitToList(str);

        for (String temp : myList) {
            System.out.println(temp);
        }
    }
}
```

**Output:**

```java
Hello
 geeks
 for
 geeks
 noida

```

**例 2:**

```java
// Java code to show implementation of
// splitToList method 
// of Guava's Splitter Class

import com.google.common.base.Splitter;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a string variable
        String str = "Everyone. should. Learn, Data. Structures";

        // SplitToList returns a List of the strings.
        // This can be transformed to an ArrayList
        // or used directly in a loop.
        List<String> myList = Splitter.on('.').splitToList(str);

        for (String temp : myList) {
            System.out.println(temp);
        }
    }
}
```

**Output:**

```java
Everyone
 should
 Learn, Data
 Structures

```