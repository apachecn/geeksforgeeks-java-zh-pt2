# 程序打印有趣的图案

> 原文:[https://www . geesforgeks . org/program-to-print-interest-pattern/](https://www.geeksforgeeks.org/program-to-print-interesting-pattern/)

打印以下图案的程序:

```java
********1********
*******2*2*******
******3*3*3******
*****4*4*4*4*****
****5*5*5*5*5****
***6*6*6*6*6*6***
**7*7*7*7*7*7*7**
```

**例:**

```java
Input : 4

Output :
********1********
*******2*2*******
******3*3*3******
*****4*4*4*4*****

Input :5

Output :
********1********
*******2*2*******
******3*3*3******
*****4*4*4*4*****
****5*5*5*5*5****
```

## C++

```java
// CPP program to print pattern
#include<bits/stdc++.h>
using namespace std;

void StarPattern(int height)
{
// This loop prints number of rows
    for (int i=0; i<height; i++ )
    {
        // For every row, first '*' will be
        // printed Height-rowNumber times.
        for (int j = height-1; j>i; j--)
        {
            cout<<"*";
        }

        // Print character '*' and Row number
        // alternately boolean variable to
        // decide whether to print char or int
        bool printChar = false;

        for (int j = 0; j< ((i*2) +1); j++)
        {
            if ( printChar )
            {
                cout<<"*";
            }
            else
            {
               cout<< (i + 1);
            }

            // Each time after printing char
            // or int reverse the boolean variable
            //  to print alternatively
                printChar = !printChar;
            }

            // After printing char and int,
            // it will print '*'
            for (int j = height-1; j>i; j--)
            {
                cout<<"*";
            }

        cout<<endl;
        }
}

// driver code
int main()
{
    int height = 7;
    StarPattern(height);

    return 0;

}

// This code is contributed by Sahil_Bansall
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to print pattern
import java.util.*;
import java.lang.*;
import java.io.*;

public class GeeksforGeeks
{

  public static void StarPattern(int height)
  {

    // This loop prints number of rows
    for (int i=0; i<height; i++ )
    {
        // For every row, first '*' will be printed
        // Height-rowNumber times.
        for (int j = height-1; j>i; j--)
        {
            System.out.print("*");
        }

        // Print character '*' and Row number alternately
        // boolean variable to decide whether to print char or int
        boolean printChar = false;

        for (int j = 0; j< ((i*2) +1); j++)
        {
            if ( printChar )
            {
                System.out.print("*");                
            }
            else
            {
            System.out.print(i + 1);
            }
            // Each time after printing char or int
            // reverse the boolean variable to print alternatively
                printChar = !printChar;
            }
            // After printing char and int, it will print '*'
            for (int j = height-1; j>i; j--)
            {
                System.out.print("*");
            }

            System.out.println();
        }
        }

    // Driver Code
    public static void main(String args[])
    {
       int height = 7;
       StarPattern(height);
    }
}
```

## 蟒蛇 3

```java
# Python program to print pattern

def StarPattern(height):

    # This loop prints number of rows
    for i in range(height):

        # For every row, first '*' will be
        # printed Height-rowNumber times.
        for j in range(height-1,i,-1):

            print("*",end="")

        # Print character '*' and Row number
        # alternately boolean variable to
        # decide whether to print char or int
        printChar = False

        for j in range(((i*2) +1)):

            if ( printChar ):

                print("*",end="")

            else:

                print(i + 1,end="")

            # Each time after printing char
            # or int reverse the boolean variable
            #  to print alternatively
            printChar = not printChar

        # After printing char and int,
        # it will print '*'
        for j in range(height-1,i,-1):

            print("*",end="")

        print()

# Driver code

height = 7
StarPattern(height)

# This code is contributed
# by Anant Agarwal.
```

## C#

```java
// C# program to print pattern
using System;
public class GeeksforGeeks {

    public static void StarPattern(int height)
    {

        // This loop prints number of rows
        for (int i = 0; i < height; i++) {

            // For every row, first '*' will be
            // printed Height-rowNumber times.
            for (int j = height - 1; j > i; j--) {
                Console.Write("*");
            }

            // Print character '*' and Row number
            // alternately boolean variable to decide
            // whether to print char or int
            bool printChar = false;

            for (int j = 0; j < ((i * 2) + 1); j++) {
                if (printChar) {
                    Console.Write("*");
                }
                else {
                    Console.Write(i + 1);
                }
                // Each time after printing char
                // or int reverse the boolean variable
                // to print alternatively
                printChar = !printChar;
            }

            // After printing char and int, it will print '*'
            for (int j = height - 1; j > i; j--) {
                Console.Write("*");
            }

            Console.WriteLine();
        }
    }

    // Driver Code
    public static void Main()
    {
        int height = 7;
        StarPattern(height);
    }
}
// This code is contributed by vt_m.
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```java
<?php
// PHP implementation to
// print pattern

function StarPattern($height)
{
    // This loop prints number
    // of rows
    for ($i = 0; $i < $height; $i++ )
    {
        // For every row, first '*'
        // will be printed
        // Height-rowNumber times.
        for ($j = $height - 1; $j > $i;
                                  $j--)
        {
            echo "*";
        }

        // Print character '*' and
        // Row number alternately
        // boolean variable to decide
        // whether to print char or int
        $printChar = false;

        for ($j = 0; $j< (($i * 2) + 1);
                                   $j++)
        {
            if ( $printChar )
            {
                echo "*";
            }
            else
            {
            echo ($i + 1);
            }

            // Each time after printing
            // char or int reverse the
            // boolean variable to print
            // alternatively
                $printChar = !$printChar;
            }

            // After printing char and int,
            // it will print '*'
            for ($j = $height-1; $j > $i;
                                    $j--)
            {
                echo "*";
            }

        echo "\n";
        }
}

// Driver code
$height = 7;
StarPattern($height);

// This code is contributed by mits
?>
```

## java 描述语言

```java
<script>
      // JavaScript program to print pattern

      function StarPattern(height)
      {

        // This loop prints number of rows
        for (var i = 0; i < height; i++)
        {

          // For every row, first '*' will be
          // printed Height-rowNumber times.
          for (var j = height + 1; j > i; j--)
          {
            document.write("*");
          }

          // Print character '*' and Row number
          // alternately boolean variable to
          // decide whether to print char or int
          var printChar = false;

          for (var j = 0; j < i * 2 + 1; j++)
          {
            if (printChar) {
              document.write("*");
            } else {
              document.write(i + 1);
            }

            // Each time after printing char
            // or int reverse the boolean variable
            // to print alternatively
            printChar = !printChar;
          }

          // After printing char and int,
          // it will print '*'
          for (var j = height + 1; j > i; j--) {
            document.write("*");
          }
          document.write("<br>");
        }
      }

      // driver code
      var height = 7;
      StarPattern(height);

      // This code is contributed by rdtank.
    </script>
```

**输出:**

```java
********1********
*******2*2*******
******3*3*3******
*****4*4*4*4*****
****5*5*5*5*5****
***6*6*6*6*6*6***
**7*7*7*7*7*7*7**
```

**方法 2(使用条件):**

我们可以使用图案的位置来识别要打印数字或“*”的位置。

例如，取高度= 5:

**1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17**

**1 * * * * * * * * 1 * * * * * * ***

**2 * * * * * * * 2 * 2 * * * * * * ***

**3 * * * * * * 3 * 3 * 3 * * * * * ***

**4 * * * * * 4 * 4 * 4 * * * * ***

**5 * * * * 5 * 5 * 5 * 5 * 5 * * * ***

现在想象我们正在打印一个装满“*”的盒子，在特定的地方我们看到数字。注意他们的位置，并观察到在所有行中，它从 i+j == 10 开始，到 j-i <= height+4\. And it is printing only when i+j is even. There we will print i when it is i+j is even and in the above-specified range. 
结束

## Java 语言(一种计算机语言，尤用于创建网站)

```java
/*package whatever //do not write package name here */

import java.io.*;

public class GFGInterestingPattern {
    public static void main(String[] args) {
        int height = 7;
          //Input for our interesting patterns height
        printPattern(height);
    }

    public static void printPattern(int height){
          //This loop prints the rows
        for(int i=1; i<=height; i++){
              //This loop prints the columns
            for(int j=1; j<=17; j++){
                  //This condition checks whether to print number or '*'
                if((i+j)%2 == 0 && i+j >= 10 && j-i <= 8) {
                    System.out.print(i);
                } else {
                    System.out.print('*');
                }
            }
              //Goes to next line
            System.out.println();
        }
    }
      //This code is contributed by Satya Anvesh R
}
```

**Output**

```java
********1********
*******2*2*******
******3*3*3******
*****4*4*4*4*****
****5*5*5*5*5****
***6*6*6*6*6*6***
**7*7*7*7*7*7*7**

```