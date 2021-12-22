# 使用正则表达式

删除句子中的重复单词

> 原文:[https://www . geesforgeks . org/remove-replicate-word-from-in-句子-使用-正则表达式/](https://www.geeksforgeeks.org/remove-duplicate-words-from-sentence-using-regular-expression/)

给定一个代表句子的字符串 **str** ，任务是使用 java 中的[正则表达式](https://www.geeksforgeeks.org/write-regular-expressions/)从句子中[移除重复的单词。
**举例:**](https://www.geeksforgeeks.org/remove-duplicaterepeated-words-string/) 

> **输入:** str = "再见世界世界"
> **输出:**再见世界
> **解释:**
> 我们把*再见*和*世界的第二次出现从再见世界
> **中去掉**输入: str =【拉姆去了去了他家】
> **输出:**拉姆去了他家
> **解释:…
> **输入:**str = " Hello hello world world "
> **输出:** Hello world
> **解释:**
> 我们从 Hello Hello world 中移除第二个出现的 *hello* 和 *world* 。***

**接近**T2】

1.  拿到句子。
2.  形成[正则表达式](https://www.geeksforgeeks.org/write-regular-expressions/)去除句子中的重复词。

```
regex = "\\b(\\w+)(?:\\W+\\1\\b)+";
```

1.  上述正则表达式的细节可以理解为:
    *   **“\ \ b”**:一个字边界。特殊情况需要边界。例如，在《我的论文很棒》中，“是”不会被匹配两次。
    *   **"\\w+"** 一字字符:【A-zA-Z _ 0-9】

    *   **"\\W+"** :非文字字符:【^\w】

    *   **"\\1"** :匹配第一组括号中匹配的内容，在本例中是(\w+)

    *   **“+”**:匹配 1 次或 1 次以上放置的任何东西

2.  用正则表达式匹配句子。在 Java 中，这可以使用 [Pattern.matcher()来完成。](https://www.geeksforgeeks.org/pattern-matchercharsequence-method-in-java-with-examples/)

3.  返回修改后的句子。

以下是上述方法的实现:

## C++

```
// C++ program to remove duplicate words
// using Regular Expression or ReGex.
#include <iostream>
#include <regex>
using namespace std;

// Function to validate the sentence
// and remove the duplicate words
string removeDuplicateWords(string s)
{

  // Regex to matching repeated words.
  const regex pattern("\\b(\\w+)(?:\\W+\\1\\b)+", regex_constants::icase);

  string answer = s;
  for (auto it = sregex_iterator(s.begin(), s.end(), pattern);
       it != sregex_iterator(); it++)
  {
      // flag type for determining the matching behavior
      // here it is for matches on 'string' objects
      smatch match;
      match = *it;
      answer.replace(answer.find(match.str(0)), match.str(0).length(), match.str(1));
  }

  return answer;
}

// Driver Code
int main()
{
  // Test Case: 1
  string str1
      = "Good bye bye world world";
  cout << removeDuplicateWords(str1) << endl;

  // Test Case: 2
  string str2
      = "Ram went went to to his home";
  cout << removeDuplicateWords(str2) << endl;

  // Test Case: 3
  string str3
      = "Hello hello world world";
  cout << removeDuplicateWords(str3) << endl;

  return 0;
}

// This code is contributed by yuvraj_chandra
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to remove duplicate words
// using Regular Expression or ReGex.

import java.util.regex.Matcher;
import java.util.regex.Pattern;

class GFG {

    // Function to validate the sentence
    // and remove the duplicate words
    public static String
    removeDuplicateWords(String input)
    {

        // Regex to matching repeated words.
        String regex
            = "\\b(\\w+)(?:\\W+\\1\\b)+";
        Pattern p
            = Pattern.compile(
                regex,
                Pattern.CASE_INSENSITIVE);

        // Pattern class contains matcher() method
        // to find matching between given sentence
        // and regular expression.
        Matcher m = p.matcher(input);

        // Check for subsequences of input
        // that match the compiled pattern
        while (m.find()) {
            input
                = input.replaceAll(
                    m.group(),
                    m.group(1));
        }
        return input;
    }

    // Driver code
    public static void main(String args[])
    {

        // Test Case: 1
        String str1
            = "Good bye bye world world";
        System.out.println(
            removeDuplicateWords(str1));

        // Test Case: 2
        String str2
            = "Ram went went to to his home";
        System.out.println(
            removeDuplicateWords(str2));

        // Test Case: 3
        String str3
            = "Hello hello world world";
        System.out.println(
            removeDuplicateWords(str3));
    }
}
```

## 蟒蛇 3

```
# Python program to remove duplicate words
# using Regular Expression or ReGex.
import re

# Function to validate the sentence
# and remove the duplicate words
def removeDuplicateWords(input):

    # Regex to matching repeated words
    regex = r'\b(\w+)(?:\W+\1\b)+'

    return re.sub(regex, r'\1', input, flags=re.IGNORECASE)

# Driver Code

# Test Case: 1
str1 = "Good bye bye world world"
print(removeDuplicateWords(str1))

# Test Case: 2
str2 = "Ram went went to to his home"
print(removeDuplicateWords(str2))

# Test Case: 3
str3 = "Hello hello world world"
print(removeDuplicateWords(str3))

# This code is contributed by yuvraj_chandra
```

**Output:** 

```
Good bye world
Ram went to his home
Hello world
```