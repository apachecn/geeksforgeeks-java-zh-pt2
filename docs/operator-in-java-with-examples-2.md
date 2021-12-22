# &Java 中的运算符，示例

> 原文:[https://www . geesforgeks . org/operator-in-Java-with-examples-2/](https://www.geeksforgeeks.org/operator-in-java-with-examples-2/)

Java 中的 **&运算符**有两个明确的功能:

1.  **As a Relational Operator:** & is used as a relational operator to check a conditional statement just like **&****& operator**. Both even give the same result, i.e. true if all conditions are true, false if any one condition is false.

    但是两者略有不同，突出了 **&操作符**的功能性:

    *   **&** **&运算符**:它只评估下一个条件，如果它之前的条件为真。如果任何条件为假，它不会进一步评估该语句。
    *   **&运算符**:它评估所有条件，即使它们是假的。因此，由于条件导致的数据值的任何变化将仅在这种情况下得到反映。

    **示例:**

    ```
    // Java program to demonstrate
    // & operator as relational operator

    import java.io.*;

    class GFG {
        public static void main(String[] args)
        {

            int x = 5, y = 7, z = 9;

            System.out.println("Demonstrating && operator");
            if ((x > y) && (x++ > z))
                ;
            else
                System.out.println("Value of x: " + x);

            System.out.println("\nDemonstrating & operator");
            if ((x > y) & (x++ > z))
                ;
            else
                System.out.println("Value of x: " + x);
        }
    }
    ```

    **Output:**

    ```
    Demonstrating && operator
    Value of x: 5

    Demonstrating & operator
    Value of x: 6

    ```

2.  **As a Bitwise AND:** **& operator** is used for adding Bitwise numbers in Java. Bitwise numbers are binary numbers stored in the form of integers. Some people will ask what is the use of these Bitwise numbers anyway? Why not store every number in its decimal form and perform the normal operations using our traditional operators: +, -, /, %, *. Its because all our encoding and decoding of data is done in bits, as they allow packing a huge amount of information into a tiny space.

    **示例:**

    ```
    // Java program to demonstrate
    // & operator as bitwise operator

    import java.io.*;

    class GFG {
        public static void main(String[] args)
        {

            int a = 12;
            int b = 25;

            System.out.println("Demonstrating & operator\n");
            int c = a & b;
            System.out.println(a + " & " + b + " = " + c);
        }
    }
    ```

    **Output:**

    ```
    Demonstrating & operator

    12 & 25 = 8

    ```