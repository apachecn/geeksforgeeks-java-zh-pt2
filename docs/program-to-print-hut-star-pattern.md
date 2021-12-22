# 打印小屋星形图案的程序

> 原文:[https://www . geesforgeks . org/program-to-print-hut-star-pattern/](https://www.geeksforgeeks.org/program-to-print-hut-star-pattern/)

给定一个数 N，使得 N >= 5。任务是打印具有(N + 3)行的小屋星形图案，如下例所示。

**示例:**

```java
Input: N = 5
Output:
        * 
      * * * 
    * * * * * 
  * * * * * * * 
* * * * * * * * * 
* * *       * * * 
* * *       * * * 
* * *       * * * 

Input: N = 7
Output:
            * 
          * * * 
        * * * * * 
      * * * * * * * 
    * * * * * * * * * 
  * * * * * * * * * * * 
* * * * * * * * * * * * * 
* * *               * * * 
* * *               * * * 
* * *               * * * 
```

**方法:**图案的上面 N 行将是一个三角形，最后 3 行将包含两个用空格分隔的矩形，如上例所示。

1.  首先[打印 N 行的上三角](https://www.geeksforgeeks.org/programs-printing-pyramid-patterns-java/)。
2.  然后把小屋下面的 2 个矩形打印成 3 行。

下面是上述方法的实现:

## C++

```java
// C++ program to print
// the Hut Star Pattern

#include <iostream>

using namespace std;

// Function to print the Hut-Star Pattern
void printHutStar(int n)
{
    int i, j;

    // Printing the upper triangle
    for (i = 0; i < n; i++) {

        // Left space triangle
        for (j = i + 1; j < n; j++)
            cout << " " ;

        // Center Star triangle
        for (j = 0; j < (2 * i + 1); j++)
            cout << "*" ;

        cout << endl ;
    }

    // Printing Lower rectangles
    for (i = 0; i < 3; i++) {

        // Left rectangle
        for (j = 0; j < 3; j++)
            cout << "*" ;

        // Center Space rectangle
        for (j = 0; j < (2 * n - 7); j++)
            cout << " " ;

        // Right rectangle
        for (j = 0; j < 3; j++)
            cout << "*" ;

        cout << endl ;
    }
}

int main()
{
int n = 7;

    // function calling
    printHutStar(n);

return 0;
// This code is contributed
// by ANKITRAI1
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to print
// the Hut Star Pattern

public class GFG {

    // Function to print the Hut-Star Pattern
    static void printHutStar(int n)
    {
        int i, j;

        // Printing the upper triangle
        for (i = 0; i < n; i++) {

            // Left space triangle
            for (j = i + 1; j < n; j++)
                System.out.print(" ");

            // Center Star triangle
            for (j = 0; j < (2 * i + 1); j++)
                System.out.print("*");

            System.out.println();
        }

        // Printing Lower rectangles
        for (i = 0; i < 3; i++) {

            // Left rectangle
            for (j = 0; j < 3; j++)
                System.out.print("*");

            // Center Space rectangle
            for (j = 0; j < (2 * n - 7); j++)
                System.out.print(" ");

            // Right rectangle
            for (j = 0; j < 3; j++)
                System.out.print("*");

            System.out.println();
        }
    }

    // Driver Code
    public static void main(String args[])
    {
        int n = 7;

        printHutStar(n);
    }
}
```

## 蟒蛇 3

```java
# Python program to print
# the Hut Star Pattern

# Function to print the Hut-Star Pattern
def printHutStar(n):

    # Printing the upper triangle
    for i in range(n):

        # Left space triangle
        for j in range(i + 1, n):
            print(' ', end = '')

        # Center Star triangle
        for j in range(0, 2 * i + 1):
            print('*', end = '')
        print()

    # Printing the lower rectangles
    for i in range(3):

        # Left rectangle
        for j in range(3):
            print('*', end = '')

        # Center Space rectangle
        for j in range(2 * n - 7):
            print(' ', end = '')

        # Right rectangle
        for j in range(3):
            print('*', end = '')
        print()

# Driver Code
n = 7

# function calling
printHutStar(n)

# This code is contributed
# by SamyuktaSHegde
```

## C#

```java
// C# program to print
// the Hut Star Pattern
using System;

class GFG {

    // Function to print the Hut-Star Pattern
    static void printHutStar(int n)
    {
        int i, j;

        // Printing the upper triangle
        for (i = 0; i < n; i++) {

            // Left space triangle
            for (j = i + 1; j < n; j++)
                Console.Write(" ");

            // Center Star triangle
            for (j = 0; j < (2 * i + 1); j++)
                Console.Write("*");

            Console.Write("\n");
        }

        // Printing Lower rectangles
        for (i = 0; i < 3; i++) {

            // Left rectangle
            for (j = 0; j < 3; j++)
                Console.Write("*");

            // Center Space rectangle
            for (j = 0; j < (2 * n - 7); j++)
                Console.Write(" ");

            // Right rectangle
            for (j = 0; j < 3; j++)
                Console.Write("*");

            Console.Write("\n");
        }
    }

    // Driver Code
    public static void Main()
    {
        int n = 7;

        printHutStar(n);
    }
}

// This code is contributed by ChitraNayal
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```java
<?php
// PHP program to print
// the Hut Star Pattern

// Function to print the Hut-Star Pattern
function printHutStar($n)
{

    // Printing the upper triangle
    for ($i = 0; $i < $n; $i++)
    {

        // Left space triangle
        for ($j = $i + 1; $j < $n; $j++)
            echo " " ;

        // Center Star triangle
        for ($j = 0; $j < (2 * $i + 1); $j++)
            echo "*" ;

        echo "\n";
    }

    // Printing Lower rectangles
    for ($i = 0; $i < 3; $i++)
    {

        // Left rectangle
        for ($j = 0; $j < 3; $j++)
            echo "*" ;

        // Center Space rectangle
        for ($j = 0; $j < (2 * $n - 7); $j++)
            echo " " ;

        // Right rectangle
        for ($j = 0; $j < 3; $j++)
            echo "*" ;

        echo "\n";
    }
}

// Driver Code
$n = 7;

// function calling
printHutStar($n);

// This code is contributed
// by Akanksha Rai
```

## java 描述语言

```java
<script>

      // JavaScript program to print
      // the Hut Star Pattern

      // Function to print the Hut-Star Pattern
      function printHutStar(n)
      {
        var i, j;

        // Printing the upper triangle
        for (i = 0; i < n; i++) {
          // Left space triangle
          for (j = i + 1; j < n; j++)
          document.write("  ");

          // Center Star triangle
          for (j = 0; j < 2 * i + 1; j++)
          document.write("*");

          document.write("<br>");
        }

        // Printing Lower rectangles
        for (i = 0; i < 3; i++) {
          // Left rectangle
          for (j = 0; j < 3; j++)
          document.write("*");

          // Center Space rectangle
          for (j = 0; j < 2 * n - 7; j++)
          document.write("  ");

          // Right rectangle
          for (j = 0; j < 3; j++)
          document.write("*");

          document.write("<br>");
        }
      }

      var n = 7;

      // function calling
      printHutStar(n);

    </script>
```

**Output:** 

```java
      *
     ***
    *****
   *******
  *********
 ***********
*************
***       ***
***       ***
***       ***
```

**另一种方法:**(降低时间复杂度)

## C++

```java
// C++ program to print
// the Hut Star Pattern

#include<iostream>
using namespace std;

int main()
{
    int n=7,i,j;

    //LOOP FOR HUT PYRAMID
    for(i=0,j=0;i<n;j++)        
    {
        if(j==n+i)
        {
            j=-1;
            ++i;
            cout<<"\n";
        }

        // print Center Star triangle
        else if((i+j)>=n-1)
        {
            cout<<"*";
        }
        else
            cout<<" ";
    }

    //LOOPS FOR LOWER WALLS
    for(int k=0;k<3;k++)        
    {
        // Left and right rectangle
        for(int l=0;l<n-1+i;l++)
        {
            if(l<=2 || (l<=n-1+i && l>=n-4+i))
                cout<<"*";
            else
                cout<<" ";
        }
        cout<<endl;
    }
}
//This code is contributed by KUMARAN
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to print the Hut Star Pattern
class GFG
{

public static void main(String args[])
{
    int n = 7, i, j;

    // LOOP FOR HUT PYRAMID
    for (i = 0, j = 0; i < n; j++)
    {
        if (j == n + i)
        {
            j = -1;
            ++i;
            System.out.print("\n");
        } // print Center Star triangle
        else if ((i + j) >= n - 1)
        {
            System.out.print("*");
        }
        else
        {
            System.out.print(" ");
        }
    }

    // LOOPS FOR LOWER WALLS
    for (int k = 0; k < 3; k++)
    {
        // Left and right rectangle
        for (int l = 0; l < n - 1 + i; l++)
        {
            if (l <= 2 || (l <= n - 1 + i &&
                           l >= n - 4 + i))
            {
                System.out.print("*");
            }
            else
            {
                System.out.print(" ");
            }
        }
        System.out.print("\n");
    }
}
}

// This code is contributed
// by PrinciRaj1992
```

## 蟒蛇 3

```java
# Python3 program to print the
# Hut Star Pattern
import math as mt

if __name__ == '__main__':

    n = 7
    i, j = 0, 0

    # LOOP FOR HUT PYRAMID
    while(i < n):    
        if(j == n + i):
            j = -1
            i += 1
            print()

        elif((i + j) >= n - 1):
            print("*", end = "")
        else:
            print(end = " ")
        j += 1

    # LOOPS FOR LOWER WALLS
    for k in range(3):   

        # Left and right rectangle
        for l in range(n - 1 + i):
            if(l <= 2 or (l <= n - 1 + i and
                          l >= n - 4 + i)):
                print("*", end = "")
            else:
                print(end = " ")

        print()

# This code is contributed by
# Mohit kumar 29
```

## C#

```java
// C# program to print the Hut Star Pattern
using System;

class GFG
{

public static void Main()
{
    int n = 7, i, j;

    // LOOP FOR HUT PYRAMID
    for (i = 0, j = 0; i < n; j++)
    {
        if (j == n + i)
        {
            j = -1;
            ++i;
            Console.Write("\n");
        } // print Center Star triangle
        else if ((i + j) >= n - 1)
        {
            Console.Write("*");
        }
        else
        {
            Console.Write(" ");
        }
    }

    // LOOPS FOR LOWER WALLS
    for (int k = 0; k < 3; k++)
    {
        // Left and right rectangle
        for (int l = 0; l < n - 1 + i; l++)
        {
            if (l <= 2 || (l <= n - 1 + i &&
                        l >= n - 4 + i))
            {
                Console.Write("*");
            }
            else
            {
                Console.Write(" ");
            }
        }
        Console.Write("\n");
    }
}
}

// This code is contributed
// by Akanksha Rai
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```java
<?php
// PHP program to print the
// Hut Star Pattern

// Driver Code
$n = 7;

// LOOP FOR HUT PYRAMID
for ($i = 0, $j = 0; $i < $n; $j++)
{
    if ($j == $n + $i)
    {
        $j = -1;
        ++$i;
        echo("\n");
    } // print Center Star triangle
    else if (($i + $j) >= $n - 1)
    {
        echo("*");
    }
    else
    {
        echo(" ");
    }
}

// LOOPS FOR LOWER WALLS
for ($k = 0; $k < 3; $k++)
{
    // Left and right rectangle
    for ($l = 0; $l < $n - 1 + $i; $l++)
    {
        if ($l <= 2 || ($l <= $n - 1 + $i &&
                        $l >= $n - 4 + $i))
        {
            echo("*");
        }
        else
        {
            echo(" ");
        }
    }
    echo("\n");
}

// This code is contributed
// by Mukul singh
?>
```

## java 描述语言

```java
<script>

// Javascript program to print the Hut Star Pattern    
var n = 7, i, j;

// LOOP FOR HUT PYRAMID
for(i = 0, j = 0; i < n; j++)
{
    if (j == n + i)
    {
        j = -1;
        ++i;
        document.write("<br/>");
    }

    // Print Center Star triangle
    else if ((i + j) >= n - 1)
    {
        document.write("*");
    }
    else
    {
        document.write("  ");
    }
}

// LOOPS FOR LOWER WALLS
for(k = 0; k < 3; k++)
{

    // Left and right rectangle
    for(l = 0; l < n - 1 + i; l++)
    {
        if (l <= 2 || (l <= n - 1 + i &&
                       l >= n - 4 + i))
        {
            document.write("*");
        }
        else
        {
            document.write("  ");
        }
    }
    document.write("<br/>");
}

// This code is contributed by umadevi9616

</script>
```

**Output:** 

```java
      *
     ***
    *****
   *******
  *********
 ***********
*************
***       ***
***       ***
***       ***
```