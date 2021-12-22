# 在 Java 中使用构造函数的用户定义异常

> 原文:[https://www . geesforgeks . org/用户定义的异常-使用 java 中的构造函数/](https://www.geeksforgeeks.org/user-defined-exceptions-using-constructors-in-java/)

在 Java 中，我们已经定义了异常类，比如 ArithmeticException、NullPointerException 等。这些异常已经被设置为在预定义的条件下触发，例如当您将一个数除以零时，它会触发算术异常。

在 Java 中，我们可以创建自己的异常类，并使用 throw 关键字抛出该异常。这些异常被称为**用户自定义**或**自定义**异常。

**问题陈述:**实现一个 Java 类 Matrix 来表示实数的二维矩阵。该类应该导出以下方法:

*   **矩阵(int n，int m):** 创建大小为 nxm 的矩阵的构造函数，所有值初始设置为 0；
*   **矩阵乘积(矩阵 m):** 如果两个矩阵具有相容的维数，则返回作为对象和 m 的乘积的矩阵，否则为空；**异常错误矩阵维度**如果矩阵的维度对于矩阵的乘法是错误的，则在方法 check()中抛出。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to create user defined
// exceptions

import java.util.Scanner;

// User defined exception class to store the exception
// message
class ExceptionWrongMatrixDimension extends Exception {

    public ExceptionWrongMatrixDimension(String str)
    {
        // stores the exception message to be displayed
        super(str);
    }
}

class twoDimensionalMatrix {

    void Matrix(int n, int m)
        throws ExceptionWrongMatrixDimension
    {
        // initialize matrix to be processed
        int[][] matrix = { { 1, 2 },
                           {
                               4,
                               5,
                           } };

        System.out.println("\nMatrix is :");

        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                System.out.print(matrix[i][j] + " ");
            }
            System.out.println();
        }

        int rows = 2;
        int cols = 2;

        if (n != rows) {

            // throw keyword for an exception in a method
            throw new ExceptionWrongMatrixDimension(
                "Invalid matrix dimensions to multiply");
        }
        else {
            int[][] m_matrix = { { 6, 3 },
                                 {
                                     9,
                                     2,
                                 } };

            System.out.println("\nMatrix to multiply is :");

            for (int i = 0; i < rows; i++) {
                for (int j = 0; j < cols; j++) {

                    System.out.print(m_matrix[i][j] + " ");
                }
                System.out.println();
            }

            System.out.println("\nMatrix to multiply is :");

            for (int i = 0; i < rows; i++) {
                for (int j = 0; j < cols; j++) {
                    System.out.print(m_matrix[i][j] + " ");
                }
                System.out.println();
            }

            int c[][] = new int[m][n];

            for (int i = 0; i < rows; i++) {
                for (int j = 0; j < rows; j++) {
                    c[i][j] = 0;
                    for (int k = 0; k < rows; k++) {
                        c[i][j] += matrix[i][j]
                                   * m_matrix[k][j];
                    }
                }
            }

            System.out.println(
                "\n\nMatrix after multiplication is");

            for (int i = 0; i < rows; i++) {
                for (int j = 0; j < cols; j++) {

                    // prints the third matrix containing
                    // the multiplied values
                    System.out.print(c[i][j] + " ");
                }
                System.out.println();
            }
        }
    }
}

public class Main {
    public static void main(String args[])
    {
        twoDimensionalMatrix matrix
            = new twoDimensionalMatrix();

        try {

            // block of code to be tested for errors while
            // it is being executed.
            System.out.println("Enter the number of rows");

            int n = 2;

            System.out.println(
                "Enter the number of columns");
            int m = 2;
            matrix.Matrix(n, m);
        }

        catch (ExceptionWrongMatrixDimension e) {

            // block of code to be executed, if an error
            // occurs in the try block.
            System.out.println(
                "ExceptionWrongMatrixDimension:");

            // returns a method object. The name parameter
            // is passed as a string.
            System.out.println(e.getMessage());
        }
    }
}
```

**Output**

```java
Enter the number of rows
Enter the number of columns

Matrix is :
1 2 
4 5 

Matrix to multiply is :
6 3 
9 2 

Matrix to multiply is :
6 3 
9 2 

Matrix after multiplication is
15 10 
60 25 
```