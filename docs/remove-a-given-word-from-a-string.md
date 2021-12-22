# 从字符串中删除给定的单词

> 原文:[https://www . geesforgeks . org/从字符串中删除给定单词/](https://www.geeksforgeeks.org/remove-a-given-word-from-a-string/)

给定一个字符串和一个单词，任务是从字符串中移除该单词。

**示例:**

```
Input: String = "Geeks For Geeks", Word = "For"
Output: "Geeks Geeks"

Input: String = "A computer Science Portal", Word = "Geeks"
Output: "A computer Science Portal"

```

**方法:**在 Java 中，这可以通过使用[字符串替换所有方法](https://www.geeksforgeeks.org/java-lang-string-replace-method-java/)用空格替换给定的单词来完成。

以下是上述问题的解决方案:

## C++

```
// C++ program to remove
// a given word from a string

#include <bits/stdc++.h>
using namespace std;

string removeWord(string str, string word) 
{
    // Check if the word is present in string
    // If found, remove it using removeAll()
    if (str.find(word) != string::npos)
    {
        size_t p = -1;

        // To cover the case
        // if the word is at the
        // beginning of the string
        // or anywhere in the middle
        string tempWord = word + " ";
        while ((p = str.find(word)) != string::npos)
            str.replace(p, tempWord.length(), "");

        // To cover the edge case
        // if the word is at the
        // end of the string
        tempWord = " " + word;
        while ((p = str.find(word)) != string::npos)
            str.replace(p, tempWord.length(), "");
    }

    // Return the resultant string
    return str;
}

// Driver Code
int main(int argc, char const *argv[]) 
{
    // Test Case 1:
    // If the word is in the middle
    string string1 = "Geeks for Geeks.";
    string word1 = "for";

    // Test Case 2:
    // If the word is at the beginning
    string string2 = "for Geeks Geeks.";
    string word2 = "for";

    // Test Case 3:
    // If the word is at the end
    string string3 = "Geeks Geeks for.";
    string word3 = "for";

    // Test Case 4:
    // If the word is not present
    string string4 = "A computer Science Portal.";
    string word4 = "Geeks";

    // Test case 1
    cout << "String: " << string1 << "\nWord: " 
         << word1 << "\nResult String: " 
         << removeWord(string1, word1) << endl;

    // Test case 2
    cout << "\nString: " << string2 << "\nWord: " 
         << word2 << "\nResult String: " 
         << removeWord(string2, word2) << endl;

    // Test case 3
    cout << "\nString: " << string3 << "\nWord: "
         << word3 << "\nResult String: " 
         << removeWord(string3, word3) << endl;

    // Test case 4
    cout << "\nString: " << string4 << "\nWord: " 
         << word4 << "\nResult String: " 
         << removeWord(string4, word4) << endl;
    return 0;
}

// This code is contributed by
// sanjeev2552
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to remove
// a given word from a string
public class GFG {
    public static String removeWord(String string, String word)
    {

        // Check if the word is present in string
        // If found, remove it using removeAll()
        if (string.contains(word)) {

            // To cover the case
            // if the word is at the
            // beginning of the string
            // or anywhere in the middle
            String tempWord = word + " ";
            string = string.replaceAll(tempWord, "");

            // To cover the edge case
            // if the word is at the
            // end of the string
            tempWord = " " + word;
            string = string.replaceAll(tempWord, "");
        }

        // Return the resultant string
        return string;
    }

    public static void main(String args[])
    {

        // Test Case 1:
        // If the word is in the middle
        String string1 = "Geeks for Geeks.";
        String word1 = "for";

        // Test Case 2:
        // If the word is at the beginning
        String string2 = "for Geeks Geeks.";
        String word2 = "for";

        // Test Case 3:
        // If the word is at the end
        String string3 = "Geeks Geeks for.";
        String word3 = "for";

        // Test Case 4:
        // If the word is not present
        String string4 = "A computer Science Portal.";
        String word4 = "Geeks";

        // Test case 1
        System.out.println("String: " + string1
                           + "\nWord: " + word1
                           + "\nResult String: "
                           + removeWord(string1, word1));

        // Test case 2
        System.out.println("\nString: " + string2
                           + "\nWord: " + word2
                           + "\nResult String: "
                           + removeWord(string2, word2));

        // Test case 3
        System.out.println("\nString: " + string3
                           + "\nWord: " + word3
                           + "\nResult String: "
                           + removeWord(string3, word3));

        // Test case 4
        System.out.println("\nString: " + string4
                           + "\nWord: " + word4
                           + "\nResult String: "
                           + removeWord(string4, word4));
    }
}
```

## C#

```
// C# program to remove
// a given word from a string
using System;

class GFG 
{
    public static String removeWord(String str, String word)
    {

        // Check if the word is present in string
        // If found, remove it using removeAll()
        if (str.Contains(word))
        {

            // To cover the case
            // if the word is at the
            // beginning of the string
            // or anywhere in the middle
            String tempWord = word + " ";
            str = str.Replace(tempWord, "");

            // To cover the edge case
            // if the word is at the
            // end of the string
            tempWord = " " + word;
            str = str.Replace(tempWord, "");
        }

        // Return the resultant string
        return str;
    }

    // Driver code
    public static void Main(String []args)
    {

        // Test Case 1:
        // If the word is in the middle
        String string1 = "Geeks for Geeks.";
        String word1 = "for";

        // Test Case 2:
        // If the word is at the beginning
        String string2 = "for Geeks Geeks.";
        String word2 = "for";

        // Test Case 3:
        // If the word is at the end
        String string3 = "Geeks Geeks for.";
        String word3 = "for";

        // Test Case 4:
        // If the word is not present
        String string4 = "A computer Science Portal.";
        String word4 = "Geeks";

        // Test case 1
        Console.WriteLine("String: " + string1
                        + "\nWord: " + word1
                        + "\nResult String: "
                        + removeWord(string1, word1));

        // Test case 2
        Console.WriteLine("\nString: " + string2
                        + "\nWord: " + word2
                        + "\nResult String: "
                        + removeWord(string2, word2));

        // Test case 3
        Console.WriteLine("\nString: " + string3
                        + "\nWord: " + word3
                        + "\nResult String: "
                        + removeWord(string3, word3));

        // Test case 4
        Console.WriteLine("\nString: " + string4
                        + "\nWord: " + word4
                        + "\nResult String: "
                        + removeWord(string4, word4));
    }
}

// This code contributed by Rajput-Ji
```

**Output:**

```
String: Geeks for Geeks.
Word: for
Result String: Geeks Geeks.

String: for Geeks Geeks.
Word: for
Result String: Geeks Geeks.

String: Geeks Geeks for.
Word: for
Result String: Geeks Geeks.

String: A computer Science Portal.
Word: Geeks
Result String: A computer Science Portal.

```