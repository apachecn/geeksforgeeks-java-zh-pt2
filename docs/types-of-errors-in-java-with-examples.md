# Java 中的错误类型及示例

> 原文:[https://www . geeksforgeeks . org/Java 错误类型示例/](https://www.geeksforgeeks.org/types-of-errors-in-java-with-examples/)

错误是用户执行的非法操作，导致程序异常工作。在编译或执行程序之前，编程错误通常不会被发现。有些错误会阻止程序被编译或执行。因此，应该在编译和执行之前删除错误。

最常见的错误可大致分类如下:

1.  <u>**Run Time Error:**</u> Run Time errors occur or we can say, are detected during the execution of the program. Sometimes these are discovered when the user enters an invalid data or data which is not relevant. Runtime errors occur when a program does not contain any syntax errors but asks the computer to do something that the computer is unable to reliably do. During compilation, the compiler has no technique to detect these kinds of errors. It is the JVM (Java Virtual Machine) which detects it while the program is running. To handle the error during the run time we can put our error code inside the try block and catch the error inside the catch block.

    **例如:**如果用户在计算机需要整数时输入字符串格式的数据，会出现运行时错误。

    **示例 1:** 除以零导致的运行时错误

    ```
    // Java program to demonstrate Runtime Error

    class DivByZero {
        public static void main(String args[])
        {
            int var1 = 15;
            int var2 = 5;
            int var3 = 0;
            int ans1 = var1 / var2;

            // This statement causes a runtime error,
            // as 15 is getting divided by 0 here
            int ans2 = var1 / var3;

            System.out.println(
                "Division of va1"
                + " by var2 is: "
                + ans1);
            System.out.println(
                "Division of va1"
                + " by var3 is: "
                + ans2);
        }
    }
    ```

    **Java 代码中的运行时错误:**

    ```
    Exception in thread "main" java.lang.ArithmeticException: / by zero
        at DivByZero.main(File.java:14)

    ```

    **示例 2:** 使用大于数组大小的索引从数组中赋值/检索值导致的运行时错误

    ```
    class RTErrorDemo {
        public static void main(String args[])
        {
            int arr[] = new int[5];

            // Array size is 5
            // whereas this statement assigns

            // value 250 at the 10th position.
            arr[9] = 250;

            System.out.println("Value assigned! ");
        }
    }
    ```

    **Java 代码中的运行时错误:**

    ```
    Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: 9
        at RTErrorDemo.main(File.java:10)

    ```

2.  <u>**Compile Time Error:**</u> Compile Time Errors are those errors which prevent the code from running because of an incorrect syntax such as a missing semicolon at the end of a statement or a missing bracket, class not found, etc. These errors are detected by the java compiler and an error message is displayed onto the screen while compiling. Compile Time Errors are sometimes also referred to as **Syntax errors**. These kind of errors are easy to spot and rectify because the java compiler finds them for you. The compiler will tell you which piece of code in the program got in trouble and its best guess as to what you did wrong. Usually, the compiler indicates the exact line where the error is, or sometimes the line just before it, however, if the problem is with incorrectly nested braces, the actual error may be at the beginning of the block. In effect, syntax errors represent grammatical errors in the use of the programming language.

    **示例 1:** 拼错变量名或方法名

    ```
    class MisspelledVar {
        public static void main(String args[])
        {
            int a = 40, b = 60;

            // Declared variable Sum with Capital S
            int Sum = a + b;

            // Trying to call variable Sum
            // with a small s ie. sum
            System.out.println(
                "Sum of variables is "
                + sum);
        }
    }
    ```

    **Java 代码编译错误:**

    ```
    prog.java:14: error: cannot find symbol
                + sum);
                  ^
      symbol:   variable sum
      location: class MisspelledVar
    1 error

    ```

    **示例 2:** 缺少分号

    ```
    class PrintingSentence {
        public static void main(String args[])
        {
            String s = "GeeksforGeeks";

            // Missing ';' at the end
            System.out.println("Welcome to " + s)
        }
    }
    ```

    **Java 代码编译错误:**

    ```
    prog.java:8: error: ';' expected
            System.out.println("Welcome to " + s)
                                                 ^
    1 error

    ```

    **示例:**缺少括号、方括号或大括号

    ```
    class MissingParenthesis {
        public static void main(String args[])
        {
            System.out.println("Printing 1 to 5 \n");
            int i;

            // missing parenthesis, should have
            // been for(i=1; i<=5; i++)
            for (i = 1; i <= 5; i++ {

                System.out.println(i + "\n");
            } // for loop ends

        } // main ends
    } // class ends
    ```

    **Java 代码编译错误:**

    ```
    prog.java:10: error: ')' expected
            for (i = 1; i <= 1 5; i++ { ^ error < pre>**示例:**选择语句或循环的格式不正确

    ```
    class IncorrectLoop {
        public static void main(String args[])
        {

            System.out.println("Multiplication Table of 7");
            int a = 7, ans;
            int i;

            // Should have been
            // for(i=1; i<=10; i++)
            for (i = 1, i <= 10; i++) {
                ans = a * i;
                System.out.println(ans + "\n");
            }
        }
    }
    ```

    **Java 代码编译错误:**

    ```
    prog.java:12: error: not a statement
            for (i = 1, i <= 2 10; i++) { ^ prog.java:12: error: ';' expected for (i="1," i <="10;" errors pre>
    ```

    ```

3.  <u>**Logical Error:**</u> A logic error is when your program compiles and executes, but does the wrong thing or returns an incorrect result or no output when it should be returning an output. These errors are detected neither by compiler nor by JVM. The Java system has no idea what your program is supposed to do, so it provides no additional information to help you find the error. Logical errors are also called Semantic Errors. These errors are caused due to an incorrect idea or concept used by a programmer while coding. Syntax errors are grammatical errors whereas, logical errors are errors arising out of an incorrect meaning.

    **例如:**如果一个程序员无意中添加了两个变量，当他或她打算对它们进行除法运算时，程序不会给出任何错误，并且会成功执行，但结果不正确。

    **示例:**意外地对变量使用了不正确的运算符来执行运算(使用“/”运算符来获取模数，而不是使用“%”)

    ```
    public class LErrorDemo {
        public static void main(String[] args)
        {
            int num = 789;
            int reversednum = 0;
            int remainder;

            while (num != 0) {

                // to obtain modulus % sign should
                // have been used instead of /
                remainder = num / 10;
                reversednum
                    = reversednum * 10
                      + remainder;
                num /= 10;
            }
            System.out.println("Reversed number is "
                               + reversednum);
        }
    }
    ```

    **Output:**

    ```
    Reversed number is 7870

    ```

    **示例:**显示错误信息

    ```
    class IncorrectMessage {
        public static void main(String args[])
        {
            int a = 2, b = 8, c = 6;
            System.out.println(
                "Finding the largest number \n");

            if (a > b && a > c)
                System.out.println(
                    a + " is the largest Number");
            else if (b > a && b > c)
                System.out.println(
                    b + " is the smallest Number");

            // The correct message should have
            // been System.out.println
            //(b+" is the largest Number");
            // to make logic
            else
                System.out.println(
                    c + " is the largest Number");
        }
    }
    ```

    **Output:**

    ```
    Finding the largest number 

    8 is the smallest Number

    ```