# Java 中使用类加减复数的程序

> 原文:[https://www . geesforgeks . org/program-to-add-and-减法-复数-使用 java 中的类/](https://www.geeksforgeeks.org/program-to-add-and-subtract-complex-numbers-using-class-in-java/)

在本文中，我们将通过创建一个复数类来尝试加减这两个复数，其中:

*   复数将在构造函数的帮助下初始化。
*   加法和减法将在函数调用的帮助下进行。
*   该函数将在另一个类的帮助下被调用。

**示例:**

```
Input: a1 = 4, b1 = 8
        a2 = 5, b2 = 7
Output: 
Sum = 9 + i15
Difference = -1 + i
Explanation:
(4 + i8) + (5 + i7)
= (4 + 5) + i(8 + 7) 
= 9 + i15
(4 + i8) - (5 + i7)
= (4 - 5) + i(8 - 7) 
= -1 - i

Input: a1 = 9, b1 = 3
        a2 = 6, b2 = 1
Output: 
Sum = 15 + i4
Difference = 3 + 2i

```

```
// Java program to add and subtract two
// complex numbers using Class

import java.util.*;

// User Defined Complex class
class Complex {

    // Declaring variables
    int real, imaginary;

    // Empty Constructor
    Complex()
    {
    }

    // Constructor to accept
    // real and imaginary part
    Complex(int tempReal, int tempImaginary)
    {
        real = tempReal;
        imaginary = tempImaginary;
    }

    // Defining addComp() method
    // for adding two complex number
    Complex addComp(Complex C1, Complex C2)
    {
        // creating temporary variable
        Complex temp = new Complex();

        // adding real part of complex numbers
        temp.real = C1.real + C2.real;

        // adding Imaginary part of complex numbers
        temp.imaginary = C1.imaginary + C2.imaginary;

        // returning the sum
        return temp;
    }

    // Defining subtractComp() method
    // for subtracting two complex number
    Complex subtractComp(Complex C1, Complex C2)
    {
        // creating temporary variable
        Complex temp = new Complex();

        // subtracting real part of complex numbers
        temp.real = C1.real - C2.real;

        // subtracting Imaginary part of complex numbers
        temp.imaginary = C1.imaginary - C2.imaginary;

        // returning the difference
        return temp;
    }

    // Function for printing complex number
    void printComplexNumber()
    {
        System.out.println("Complex number: "
                           + real + " + "
                           + imaginary + "i");
    }
}

// Main Class
public class GFG {

    // Main function
    public static void main(String[] args)
    {

        // First Complex number
        Complex C1 = new Complex(3, 2);

        // printing first complex number
        C1.printComplexNumber();

        // Second Complex number
        Complex C2 = new Complex(9, 5);

        // printing second complex number
        C2.printComplexNumber();

        // for Storing the sum
        Complex C3 = new Complex();

        // calling addComp() method
        C3 = C3.addComp(C1, C2);

        // printing the sum
        System.out.print("Sum of ");
        C3.printComplexNumber();

        // calling subtractComp() method
        C3 = C3.subtractComp(C1, C2);

        // printing the difference
        System.out.print("Difference of ");
        C3.printComplexNumber();
    }
}
```

**Output:**

```
Complex number: 3 + 2i
Complex number: 9 + 5i
Sum of Complex number: 12 + 7i
Difference of Complex number: -6 + -3i

```