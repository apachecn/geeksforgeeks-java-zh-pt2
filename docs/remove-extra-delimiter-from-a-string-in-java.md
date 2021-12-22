# 在 Java 中删除字符串中的额外分隔符

> 原文:[https://www . geesforgeks . org/remove-Java 字符串中的额外分隔符/](https://www.geeksforgeeks.org/remove-extra-delimiter-from-a-string-in-java/)

给定一个末尾有额外分隔符的字符串，任务是在 Java 中移除这个额外的分隔符。

**例:**

```java
Input: String = "Geeks, For, Geeks, ", delimiter = ', '
Output: "Geeks, For, Geeks"

Input: String = "G.e.e.k.s.", delimiter = '.'
Output: "G.e.e.k.s"

```

**进场:**

1.  Take the string.
2.  Use the last index of () method to get the last index of the separator.
3.  用两个不同的子字符串构造一个新的字符串:一个从开始到找到的索引–1，另一个从索引+ 1 到结束。

    下面是上述方法的实现:

    ```java
    // Java program to remove
    // extra delimiter at the end of a String

    public class GFG {

        public static void main(String args[])
        {

            // Get the String
            String str = "Geeks, For, Geeks,";

            // Get the delimiter
            char delimiter = ',';

            // Print the original string
            System.out.println("Original String: "
                               + str);

            // Get the index of  delimiter
            int index = str.lastIndexOf(delimiter);

            // Remove the extra delimiter by skipping it
            str = str.substring(0, index)
                  + str.substring(index + 1);

            // Print the new String
            System.out.println("String with extra "
                               + "delimiter removed: "
                               + str);
        }
    }
    ```

    **输出:**

    ```java
    Original String: Geeks, For, Geeks,
    String with extra delimiter removed: Geeks, For, Geeks

    ```