# 浮点数比较中的问题以及如何正确比较？

> 原文:[https://www . geeksforgeeks . org/比较浮点数时遇到的问题以及如何正确比较它们/](https://www.geeksforgeeks.org/problem-in-comparing-floating-point-numbers-and-how-to-compare-them-correctly/)

在本文中，我们将了解比较浮点数的问题，并讨论比较两个浮点数的正确方法。
**<u>通常比较浮点数有什么问题？</u>**
我们先借助 [**关系运算符(==)**](https://www.geeksforgeeks.org/java-relational-operators-with-examples/) 比较两个浮点数。
**示例:**使用“==”进行比较

## 卡片打印处理机（Card Print Processor 的缩写）

```java
// C++ program to compare
// floating point numbers

#include <bits/stdc++.h>
using namespace std;

void compareFloatNum(double a, double b)
{
    if (a == b) {
        cout << "The numbers are equal"
             << endl;
    }
    else {
        cout << "The numbers are not equal"
             << endl;
    }
}

// Driver code
int main()
{
    double a = (0.3 * 3) + 0.1;
    double b = 1;
    compareFloatNum(a, b);
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to compare
// floating point numbers
class GFG
{

    static void compareFloatNum(double a, double b)
    {
        if (a == b)
        {
            System.out.print("The numbers are equal" + "\n");
        }
        else
        {
            System.out.print("The numbers are not equal" + "\n");
        }
    }

    // Driver code
    public static void main(String[] args)
    {
        double a = (0.3 * 3) + 0.1;
        double b = 1;
        compareFloatNum(a, b);
    }
}

// This code is contributed by 29AjayKumar
```

## 计算机编程语言

```java
# Python program to compare
# floating point numbers
def compareFloatNum(a, b):
    if (a == b):
        print("The numbers are equal")

    else:
        print("The numbers are not equal")

# Driver code

a = (0.3 * 3) + 0.1
b = 1
compareFloatNum(a, b)

# This code is contributed by mohit kumar 29
```

## C#

```java
// C# program to compare
// floating point numbers
using System;

class GFG
{

    static void comparefloatNum(double a, double b)
    {
        if (a == b)
        {
            Console.Write("The numbers are equal" + "\n");
        }
        else
        {
            Console.Write("The numbers are not equal" + "\n");
        }
    }

    // Driver code
    public static void Main(String[] args)
    {
        double a = (0.3 * 3) + 0.1;
        double b = 1;
        comparefloatNum(a, b);
    }
}

// This code is contributed by PrinciRaj1992
```

## java 描述语言

```java
<script>

function compareFloatNum(a,b)
{
    if (a == b)
        {
            document.write("The numbers are equal" + "<br>");
        }
        else
        {
            document.write("The numbers are not equal" + "<br>");
        }
}

let a = (0.3 * 3) + 0.1;
 let b = 1;
 compareFloatNum(a, b);

// This code is contributed by patel2127

</script>
```

**Output:** 

```java
The numbers are not equal
```

**<u>为什么会出现这个问题？</u>**
在浮点数的情况下， [**关系运算符(==)**](https://www.geeksforgeeks.org/java-relational-operators-with-examples/) 不会产生正确的输出，这是由于浮点数舍入时的内部精度错误。
在上面的例子中，我们可以看到使用“==”运算符比较两个浮点数的不准确性。两个数字“a”和“b”相等(如(0.3 * 3) + 0.1 = 1)，但程序导致不正确的输出。
让我们仔细看看下一个片段中的数字。

## 卡片打印处理机（Card Print Processor 的缩写）

```java
// C++ program to compare
// floating point numbers

#include <bits/stdc++.h>
using namespace std;

void printFloatNum(double a, double b)
{
    // To print decimal numbers up to 20 digits
    cout << setprecision(20);

    cout << "a is : " << a << endl;
    cout << "b is : " << b << endl;
}

// Driver code
int main()
{
    double a = (0.3 * 3) + 0.1;
    double b = 1;
    printFloatNum(a, b);
}
```

## 蟒蛇 3

```java
# Python 3 program to compare
# floating point numbers
def printFloatNum(a,  b):

    # To print decimal numbers up to 20 digits
    print("a is : %.20f" %a)
    print("b is : %.20f" %b)

# Driver code
if __name__ == "__main__":

    a = (0.3 * 3) + 0.1
    b = 1
    printFloatNum(a, b)

    # This code is contributed by ukasp.
```

**Output:** 

```java
a is : 0.99999999999999988898
b is : 1
```