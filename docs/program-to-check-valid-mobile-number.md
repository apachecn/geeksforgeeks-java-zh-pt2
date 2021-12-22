# 检查有效手机号码的程序

> 原文:[https://www . geeksforgeeks . org/待查程序-有效-手机号码/](https://www.geeksforgeeks.org/program-to-check-valid-mobile-number/)

**手机号码验证标准:**

*   第一个数字应该包含 7 到 9 之间的数字。
*   其余 9 位可以包含 0 到 9 之间的任何数字。
*   手机号码也可以有 11 位数字，在开头包括 0。
*   手机号码可以是 12 位数字，也可以在起始处包含 91

满足上述标准的号码是有效的手机号码。
示例:

```java
Input : Enter Mobile Number:
        7873923408
Output :Valid Mobile Number

Input : Enter Mobile Number:
        5678729234
Output :Invalid Mobile Number
```

先决条件: [Java 正则表达式](https://www.geeksforgeeks.org/regular-expressions-in-java/)

## C++

```java
// C++ program to check if given mobile number
// is valid.
#include <iostream>
#include <regex>
using namespace std;

bool isValid(string s)
{
    // The given argument to pattern()
    // is regular expression. With the help of
    // regular expression we can validate mobile
    // number.
    // 1) Begins with 0 or 91
    // 2) Then contains 7 or 8 or 9.
    // 3) Then contains 9 digits
  const regex pattern("(0|91)?[7-9][0-9]{9}");

  // regex_match() is used to
  // to find match between given number
  // and regular expression
  if(regex_match(s, pattern))
  {
    return true;
  }
  else
  {
    return false;
  }
}

// Driver Code
int main()
{
  string s = "347873923408";
  if(isValid(s))
  {
      cout << "Valid";
  }
  else
  {
      cout<<"Invalid";
  }
  return 0;
}

// This code is contributed by yuvraj_chandra
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to check if given mobile number
// is valid.
import java.util.regex.*;
import java.util.Scanner;

class GFG{

public static boolean isValid(String s)
{

    // The given argument to compile() method 
    // is regular expression. With the help of 
    // regular expression we can validate mobile
    // number. 
    // 1) Begins with 0 or 91
    // 2) Then contains 7 or 8 or 9.
    // 3) Then contains 9 digits
    Pattern p = Pattern.compile("(0|91)?[7-9][0-9]{9}");

    // Pattern class contains matcher() method
    // to find matching between given number 
    // and regular expression
    Matcher m = p.matcher(s);
    return (m.find() && m.group().equals(s));
}

// Driver code
public static void main(String[] args)
{
    String s = "347873923408";

    if (isValid(s)) 
        System.out.println("Valid Number");     
    else
        System.out.println("Invalid Number");     
}
}
```

## 计算机编程语言

```java
# Python program to check if 
# given mobile number is valid
import re

def isValid(s):

    # 1) Begins with 0 or 91
    # 2) Then contains 7 or 8 or 9.
    # 3) Then contains 9 digits
    Pattern = re.compile("(0|91)?[7-9][0-9]{9}")
    return Pattern.match(s)

# Driver Code
s = "347873923408"
if (isValid(s)): 
    print ("Valid Number")     
else :
    print ("Invalid Number") 

# This code is contributed by rishabh_jain 
```

**输出:**

```java
Invalid Number
```