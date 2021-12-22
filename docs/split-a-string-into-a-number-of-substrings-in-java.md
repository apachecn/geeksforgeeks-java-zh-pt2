# 在 Java 中将一个字符串拆分成多个子字符串

> 原文:[https://www . geesforgeks . org/split-a-string-in-a-number-substrings-in-Java/](https://www.geeksforgeeks.org/split-a-string-into-a-number-of-substrings-in-java/)

给定一个字符串，任务是将该字符串拆分成多个[子字符串](https://www.geeksforgeeks.org/substring-in-java/)。

java 中的字符串可以包含 0 个或更多字符。

**示例:**

```
(a) "" is a String in java with 0 character
(b) "d" is a String in java with 1 character
(c) "This is a sentence." is a string with 19 characters.

```

**子串**:属于另一个字符串的一部分的字符串称为另一个字符串的子串。

**例 1:** 我们来考虑一下弦**蝙蝠**。可能的子字符串有:

```
(1) "b"
(2) "ba"
(3) "bat", every string is a substring of itself
(4) "a"
(5) "at"
(6) "t"
(7) ""  , "" is a substring of every string

```

**例 2:** 我们来考虑一下弦**猫**。可能的子字符串有:

```
(1) "T"
(2) "Th"
(3) "The"
(4) "The "
(5) "The C"
(6) "The Ca"
(7) "The Cat", every string is a substring of itself
(8) "h"
(9) "he"
(10) "he "
(11) "he C"
(12) "he Ca"
(13) "he Cat"
(14) "e"
(15) "e "
(16) "e C"
(17) "e Ca"
(18) "e Cat"
(19) " "
(20) " C"
(21) " Ca"
(22) " Cat"
(23) "C"
(24) "Ca"
(25) "Cat"
(26) "a"
(27) "at"
(28) "t"
(29) ""  , "" is a substring of every string

```

**注:**总一串长度的子串数 **N** 为 **(N * (N + 1)) / 2** 。这是在排除空字符串 **""** 之后，因为它是所有字符串的子串。

**进场:**

```
Let us consider a string which has n characters:
1\. For each character at index i (0 to n-1):
        find substrings of length 1, 2, ..., n-i

Example: Let our string be cat, here n = 3 (the length of string)
here, 
    index of 'c' is 0
    index of 'a' is 1
    index of 't' is 2

Loop from i = 0 to 2: (since n-1 = 2)

When i = 0:
    Substring of length 1 : "c"   
    Substring of length 2 : "ca" 
    Substring of length 3 : "cat" , (substring of length n-i or 3-0 = 3)

When i = 1:
    Substring of length 1 : "a"
    Substring of length 2 : "at" , (substring of length n-i or 3-1 = 2)

When i = 2:
    Substring of length 1 : "t" , (substring of length n-i or 3-2 = 1)

```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to split a string into all possible
// substrings excluding the string with 0 characters i.e. ""

import java.io.*;
import java.util.ArrayList;

class SubstringsOfAString {

    // function to split a string into all its substrings
    // and return the list as an object of ArrrayList
    public static ArrayList<String>
    splitSubstrings(String s)
    {

        // variables to traverse through the
        // string
        int i, j;

        // to store the length of the
        // string
        int stringLength = s.length();

        // List object to store the list of
        // all substrings of the string s
        ArrayList<String> subStringList
            = new ArrayList<String>();

        // first for loop
        for (i = 0; i < stringLength; i++) {

            for (j = i + 1; j <= stringLength; j++) {

                subStringList.add(s.substring(i, j));
            }

        } // end of first for loop

        // returning the list (object
        // of ArrayList) of substrings
        // of string s
        return subStringList;
    }

    public static void main(String[] args)
    {

        // here "The Cat" is our input string
        String stringInput = new String("The Cat");

        ArrayList<String> subStringList
            = SubstringsOfAString.splitSubstrings(
                stringInput);

        System.out.println(
            "\nSubstring list printed as an ArrayList : ");
        System.out.println(subStringList);

        System.out.println(
            "\n\nAll substrings printed 1 per line : ");
        int count = 1;

        // each substring would be printed
        // within double quotes
        for (String it : subStringList) {
            System.out.println("(" + count + ") \"" + it
                               + "\"");
            count++;
        }
    }
}
```

**Output**

```
Substring list printed as an ArrayList : 
[T, Th, The, The , The C, The Ca, The Cat, h, he, he , he C, he Ca, he Cat, e, e , e C, e Ca, e Cat,  ,  C,  Ca,  Cat, C, Ca, Cat, a, at, t]

All substrings printed 1 per line : 
(1) "T"
(2) "Th"
(3) "The"
(4) "The "
(5) "The C"
(6) "The Ca"
(7) "The Cat"
(8) "h"
(9) "he"
(10) "he "
(11) "he C"
(12) "he Ca"
(13) "he Cat"
(14) "e"
(15) "e "
(16) "e C"
(17) "e Ca"
(18) "e Cat"
(19) " "
(20) " C"
(21) " Ca"
(22) " Cat"
(23) "C"
(24) "Ca"
(25) "Cat"
(26) "a"
(27) "at"
(28) "t"

```

**时间复杂度** : O(n <sup>2</sup> )其中 **n** 是一根弦的长度

**输出 1:** 当字符串输入= **蝙蝠**

```
Substring list printed as an ArrayList : 
[b, ba, bat, a, at, t]

All substrings printed 1 per line : 
(1) "b"
(2) "ba"
(3) "bat"
(4) "a"
(5) "at"
(6) "t"

```

**输出 2:** 当字符串输入= **猫**

```
Substring list printed as an ArrayList : 
[T, Th, The, The , The C, The Ca, The Cat, h, he, he , he C, he Ca, he Cat, e, e , e C, e Ca, e Cat,  ,  C,  Ca,  Cat, C, Ca, Cat, a, at, t]

All substrings printed 1 per line : 
(1) "T"
(2) "Th"
(3) "The"
(4) "The "
(5) "The C"
(6) "The Ca"
(7) "The Cat"
(8) "h"
(9) "he"
(10) "he "
(11) "he C"
(12) "he Ca"
(13) "he Cat"
(14) "e"
(15) "e "
(16) "e C"
(17) "e Ca"
(18) "e Cat"
(19) " "
(20) " C"
(21) " Ca"
(22) " Cat"
(23) "C"
(24) "Ca"
(25) "Cat"
(26) "a"
(27) "at"
(28) "t"

```