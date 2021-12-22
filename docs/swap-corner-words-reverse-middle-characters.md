# 互换角字，反转中间字符

> 原文:[https://www . geesforgeks . org/swap-corner-word-reverse-middle-characters/](https://www.geeksforgeeks.org/swap-corner-words-reverse-middle-characters/)

编写一个 Java 程序，获取一个输入字符串，交换第一个和最后一个单词，并反转中间的单词。

示例:

```
Input : Hello World GFG Welcomes You
Output :You semocleW GFG dlroW Hello
```

**方法:**

*   We first take two empty strings, the first string takes the first word, and the second string takes the last word.
*   When we iterate over each word, we must pay attention to the variables that point to the next word except the last word.
*   Now we reverse the left string in the given string.
*   After the above process, we first print the last word and the reverse of the left string, and then print the first word.

## c++

```
// C++ Program to illustrate the solution
// of above problem
#include <iostream>
using namespace std;

void print(string s)
{

    // Taking an Empty String
    string fst = "";
    int i = 0;
    for (i = 0; i < s.length();) {

        // Iterating from starting index
        // When we get space, loop terminates
        while (s[i] != ' ') {
            fst = fst + s[i];
            i++;
        }

        // After getting one Word
        break;
    }

    // Taking an Empty String
    string last = "";
    int j = 0;
    for (j = s.length() - 1; j >= i;) {

        // Iterating from last index
        // When we get space, loop terminates
        while (s[j] != ' ') {
            last = s[j] + last;
            j--;
        }

        // After getting one Word
        break;
    }

    // Printing last word
    cout<<last;
    for (int m = j; m >= i; m--) {

        // Reversing the left characters
        cout<<s[m];
    }

    // Printing the first word
    cout<<fst;
}

int main() {

    string s = "Hello World GFG Welcomes You";
    print(s);

    return 0;
}

//This code is contributed by vt_m.
```

## Java

```
// Java Program to illustrate the solution of above problem
public class ExchangeFirstLastReverseMiddle {
    static void print(String s)
    {
        // Taking an Empty String
        String fst = "";
        int i = 0;
        for (i = 0; i < s.length();) {

            // Iterating from starting index
            // When we get space, loop terminates
            while (s.charAt(i) != ' ') {
                fst = fst + s.charAt(i);
                i++;
            }

            // After getting one Word
            break;
        }

        // Taking an Empty String
        String last = "";
        int j = 0;
        for (j = s.length() - 1; j >= i;) {

            // Iterating from last index
            // When we get space, loop terminates
            while (s.charAt(j) != ' ') {
                last = s.charAt(j) + last;
                j--;
            }

            // After getting one Word
            break;
        }

        // Printing last word
        System.out.print(last);
        for (int m = j; m >= i; m--) {

            // Reversing the left characters
            System.out.print(s.charAt(m));
        }

        // Printing the first word
        System.out.println(fst);
    }

    public static void main(String[] args)
    {
        String s = "Hello World GFG Welcomes You";
        print(s);
    }
}
```

## python 3

```
# Python3 Program to illustrate the solution
# of above problem
def Print(s) :

    # Taking an Empty String
    fst = ""
    i = 0
    while(i < len(s)) :

        # Iterating from starting index
        # When we get space, loop terminates
        while (s[i] != ' ') :
            fst = fst + s[i]
            i += 1

        # After getting one Word
        break

    # Taking an Empty String
    last = ""
    j = len(s) - 1
    while(j >= i) :

        # Iterating from last index
        # When we get space, loop terminates
        while (s[j] != ' ') :
            last = s[j] + last
            j -= 1

        # After getting one Word
        break

    # Printing last word
    print(last, end = "")
    m = j
    while m >= i :

        # Reversing the left characters
        print(s[m] , end = "")
        m -= 1

    # Printing the first word
    print(fst, end = "")

# Driver code
s = "Hello World GFG Welcomes You"
Print(s)

# This code is contributed by divyeshrabadiya07
```

## c#

```
// C# Program to illustrate the
//solution of above problem
using System;

class ExchangeFirstLastReverseMiddle
{
    static void print(string s)
    {
        // Taking an Empty String
        string fst = "";
        int i = 0;
        for (i = 0; i < s.Length;) {

            // Iterating from starting index
            // When we get space, loop terminates
            while (s[i] != ' ')
            {
                fst = fst + s[i];
                i++;
            }

            // After getting one Word
            break;
        }

        // Taking an Empty String
        string last = "";
        int j = 0;
        for (j = s.Length - 1; j >= i;) {

            // Iterating from last index
            // When we get space, loop terminates
            while (s[j] != ' ') {
                last = s[j] + last;
                j--;
            }

            // After getting one Word
            break;
        }

        // Printing last word
        Console.Write(last);
        for (int m = j; m >= i; m--) {

            // Reversing the left characters
            Console.Write(s[m]);
        }

        // Printing the first word
        Console.Write(fst);
    }

    // Driver code
    public static void Main()
    {
        string s = "Hello World GFG Welcomes You";
        print(s);
    }
}

//This code is contributed by vt_m
```

T33】

**输出:**

```
You semocleW GFG dlroW Hello
```