# Splitter with keyvalueseparator(char separator)方法|番石榴| Java

> 原文:[https://www . geesforgeks . org/splitter-with keyvalueseparator char-separator-method-guava-Java/](https://www.geeksforgeeks.org/splitter-withkeyvalueseparatorchar-separator-method-guava-java/)

番石榴的[分割器类](https://www.geeksforgeeks.org/splitter-class-guava-java/)的**with KeyValue separator(char separator)**方法接受一个强制参数*分割器*，并使用该分割器将条目分割成键和值。

**语法:**

> 公共拆分器。带键值分隔符的映射拆分器(字符分隔符)

**参数:**该方法接受参数**分隔符**，并使用该分隔符将条目拆分为键和值。

**返回值:**该方法返回一个**地图拆分器**，它根据这个拆分器拆分条目。

**注意:**我们将成对的分隔符传递给这个方法。on()方法接收键和值对之间的分隔符。

下面的例子说明了番石榴的 Splitter 类的 withKeyValueSeparator()方法的实现:

**例 1:**

```java
// Java code to show implementation of
// withKeyValueSeparator(char separator) method
// of Guava's Splitter Class

import com.google.common.base.Splitter;
import java.util.Map;
import java.util.Map.Entry;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // This String contains key-value pairs.
        String value
            = "Data Structures=Coding,Sports=Football,Capital=Delhi";

        // Using Splitter to parse key-value separators.
        // This returns a MapSplitter which splits
        // entries based on this splitter, and splits
        // entries into keys and
        // values using the specified separator.
        Map<String, String>
            mp
            = Splitter.on(',')
                  .withKeyValueSeparator('=')
                  .split(value);

        // Looping over entries stored in map mp.
        for (Entry<String, String> entry : mp.entrySet()) {

            // Displaying key and value pairs
            System.out.println(entry.getKey() + " -> "
                               + entry.getValue());
        }
    }
}
```

**Output:**

```java
Data Structures -> Coding
Sports -> Football
Capital -> Delhi

```

**例 2:**

```java
// Java code to show implementation of
// withKeyValueSeparator(char separator) method
// of Guava's Splitter Class

import com.google.common.base.Splitter;
import java.util.Map;
import java.util.Map.Entry;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // This String contains key-value pairs.
        String value
            = "First=I.Second=II.Third=III.Fourth=IV";

        // Using Splitter to parse key-value separators.
        // This returns a MapSplitter which splits
        // entries based on this splitter, and splits
        // entries into keys and values
        // using the specified separator.
        Map<String, String>
            mp
            = Splitter.on('.')
                  .withKeyValueSeparator('=')
                  .split(value);

        // Looping over entries stored in map mp.
        for (Entry<String, String> entry : mp.entrySet()) {

            // Displaying key and value pairs
            System.out.println(entry.getKey() + " -> "
                               + entry.getValue());
        }
    }
}
```

**Output:**

```java
First -> I
Second -> II
Third -> III
Fourth -> IV

```