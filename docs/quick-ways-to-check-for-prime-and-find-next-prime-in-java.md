# 在 Java 中检查 Prime 和查找下一个 Prime 的快速方法

> 原文:[https://www . geeksforgeeks . org/快速查找质数并在 java 中找到下一个质数/](https://www.geeksforgeeks.org/quick-ways-to-check-for-prime-and-find-next-prime-in-java/)

许多编程竞赛问题都与质数有关。要么要求我们检查质数，要么要求我们对 1 到 n 之间的所有质数执行某些功能。示例:计算 1 到 1000000 之间的所有质数的总和。

Java 在 [java.math.BigInteger](https://www.geeksforgeeks.org/biginteger-class-in-java/) 下提供了两个处理素数的函数。

*   **isProbablePrime(int certainty):** A method in [BigInteger class](https://www.geeksforgeeks.org/biginteger-class-in-java/) to check if a given number is prime. For certainty = 1, it return true if BigInteger is prime and false if BigInteger is composite.

    下面是演示上述功能的 Java 程序。

    ```
    // A Java program to check if a number is prime using
    // inbuilt function
    import java.util.*;
    import java.math.*;

    class CheckPrimeTest
    {
        //Function to check and return prime numbers
        static boolean checkPrime(long n)
        {
            // Converting long to BigInteger
            BigInteger b = new BigInteger(String.valueOf(n));

            return b.isProbablePrime(1);
        }

        // Driver method
        public static void main (String[] args)
                             throws java.lang.Exception
        {
           long n = 13;
           System.out.println(checkPrime(n));
        }
    }
    ```

    输出:

    ```
    true
    ```

    *   **nextProbablePrime()** : Another method present in BigInteger class. This functions returns the next Prime Number greater than current BigInteger.

    下面是演示上述功能的 Java 程序。

    ```
    // Java program to find prime number greater than a
    // given number using built in method
    import java.util.*;
    import java.math.*;

    class NextPrimeTest
    {
        // Function to get nextPrimeNumber
        static long nextPrime(long n)
        {
            BigInteger b = new BigInteger(String.valueOf(n));
            return Long.parseLong(b.nextProbablePrime().toString());
        }

        // Driver method
        public static void main (String[] args)
                        throws java.lang.Exception
        {
            long n = 14;
            System.out.println(nextPrime(n));
        }
    }
    ```

    输出:

    ```
    17
    ```

    本文由 **Ayush Jain** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的主题的信息，请写评论