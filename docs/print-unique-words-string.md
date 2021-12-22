# 打印字符串的所有唯一单词

> 原文:[https://www.geeksforgeeks.org/print-unique-words-string/](https://www.geeksforgeeks.org/print-unique-words-string/)

编写一个函数，将一个字符串作为参数，并打印其中所有唯一的单词。

**示例:**

```
Input : Java is great. Grails is also great
Output : Java
         Grails
         also
```

**方法:**
想法是用地图记录已经发生的单词。但是首先，我们必须从一个字符串中提取所有的单词，因为一个字符串可能包含许多带有标点符号的句子。
从字符串中提取单词，请参考[从字符串中提取每个单词](https://www.geeksforgeeks.org/extracting-word-string-java/)。

**Python:** 想法是用一个[字典](https://www.geeksforgeeks.org/python-dictionary/)来计算每个单词的计数。但是首先，我们必须从字符串中提取所有单词，因为字符串可能包含标点符号。这是使用正则表达式完成的。字典中数为 1 的单词是一个独特的单词。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to print unique words
// from a string

import java.util.HashMap;
import java.util.Iterator;
import java.util.Set;
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class Test
{
    // Prints unique words in a string
    static void printUniquedWords(String str)
    {
        // Extracting words from string
        Pattern p = Pattern.compile("[a-zA-Z]+");
        Matcher m = p.matcher(str);

        // Map to store count of a word
        HashMap<String, Integer> hm = new HashMap<>();

        // if a word found
        while (m.find())
        {
            String word = m.group();

            // If this is first occurrence of word
            if(!hm.containsKey(word))
                hm.put(word, 1);
            else
                // increment counter of word
                hm.put(word, hm.get(word) + 1);

        }

        // Traverse map and print all words whose count
        // is  1
        Set<String> s = hm.keySet();
        Iterator<String> itr = s.iterator();

        while(itr.hasNext())
        {
            String w = itr.next();

            if (hm.get(w) == 1)
                System.out.println(w);
        }   
    }

    // Driver Method
    public static void main(String[] args)
    {
        String str = "Java is great. Grails is also great";
        printUniquedWords(str);
    }
}
```

## 计算机编程语言

```
# Python program to print unique word
# in a string.
# Using re (Regular Expression module)
# It is used here to match a pattern
# in the given string
import re

# Declare a dictionary
dict = {}

# Method to check whether the word
# exists in dictionary or not
def uniqueWord(Word):

    if Word in dict:

        # If the word exists in dictionary then
        # simply increase its count
        dict[words] += 1

    else:

        # If the word does not exists in
        # dictionary update the dictionary
        # and make its count 1
        dict.update({words: 1})

# Driver code
if __name__ == '__main__':

    string = "Java is great. Grails is also great"

    # re.split() method is used to split
    # all the words in a string separated
    # by non-alphanumeric characters (\W)
    ListOfWords = re.split("[\W]+", string)

    # Extract each word from ListOfWords
    # and pass it to the method uniqueWord()
    for words in ListOfWords:
        uniqueWord(words)

    # Iterate over dictionary if the value
    # of the key is 1, then print the element
    for elements in dict:
        if dict[elements] == 1:
            print(elements)
```

**Output:** 

```
Java
Grails
also
```

本文由**高拉夫·阿赫瓦尔****高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。

**方法二:使用 set()**

**进场:**

在这种方法中，我们以一组单个单词的形式存储字符串，并打印单词。用这种方法解决这个问题，首先需要了解[https://www.geeksforgeeks.org/sets-in-python/](https://www.geeksforgeeks.org/sets-in-python/)

下面是上述方法的实现:

## 蟒蛇 3

```
# python program to print all
# the unique words in a string
# in python using set() method
# function to print unique words

def printWords(l):

    # for loop for iterating
    for i in l:
        print(i)

# Driver code
str = "geeks for geeks"

# storing string in the form of list of words
s = set(str.split(" "))

# passing list to print words function
printWords(s)
```

**Output**

```
geeks
for
```