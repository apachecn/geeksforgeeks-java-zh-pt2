# Java 中的随机与安全随机数

> 原文:[https://www . geesforgeks . org/random-vs-secure-random-numbers-Java/](https://www.geeksforgeeks.org/random-vs-secure-random-numbers-java/)

先决条件:[在 Java 中生成随机数](https://www.geeksforgeeks.org/generating-random-numbers-in-java/)
**Java . security . securerandom 类:**这个类提供了一个密码强随机数生成器(RNG)。密码强随机数至少符合 FIPS 140-2《密码模块的安全要求》第 4.9.1 节中规定的统计随机数发生器测试。此外，安全对象必须产生非确定性的输出。因此，传递给安全对象的任何种子材料都必须是不可预测的，并且所有安全对象输出序列都必须是强加密的。
**Java . util . Random class:**在 Random 中定义的类不是密码学意义上的强类，选择的数字不是完全随机的，因为使用了确定的数学算法(基于 Donald E. Knuth 的减法随机数生成器算法)来选择它们。因此，将此类用于需要高度安全性的任务是不安全的，例如创建随机密码等。

**随机 vs 安全世界**

1.  **大小:**随机类只有 48 位，而安全类最多可以有 128 位。所以在安全世界中重复的机会更小。
2.  **种子生成:** Random 使用系统时钟作为种子/或生成种子。因此，如果攻击者知道种子产生的时间，它们很容易被复制。但是 SecureRandom 从您的操作系统中获取随机数据(它们可以是击键间隔等——大多数操作系统收集这些数据并将其存储在文件中——在 linux/solaris 的情况下是/dev/random 和/dev/urandom ),并将其用作种子。
3.  **破解密码:**在随机的情况下，只需要 2^48 的尝试，有了今天先进的 cpu 就有可能在实际时间内破解。但是对于安全世界来说，2^128 的尝试将是必需的，这将需要很多年才能与今天的先进机器持平。
4.  **生成函数:**标准的 Oracle JDK 7 实现使用所谓的线性同余生成器来生成 java.util.Random 中的随机值，而 Secure Random 实现 SHA1PRNG 算法，该算法使用 SHA1 来生成伪随机数。该算法通过一个真正的随机数(使用一个熵源)计算 SHA-1 散列，然后将其与一个 64 位计数器连接起来，该计数器在每次操作时递增 1。
5.  **安全性:**因此，Java . util . random 类不得用于安全关键应用程序或保护敏感数据。

**使用 java.util.Random 生成随机数；**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// A Java program to demonstrate
// random number generation
// using java.util.Random;
import java.util.Random;

public class generateRandom {

    public static void main(String args[])
    {
        // create instance of Random class
        Random rand = new Random();

        // Generate random integers in range 0 to 999
        int rand_int1 = rand.nextInt(1000);
        int rand_int2 = rand.nextInt(1000);

        // Print random integers
        System.out.println("Random Integers: " + rand_int1);
        System.out.println("Random Integers: " + rand_int2);
    }
}
```

**输出:**

```java
Random Integers: 956
Random Integers: 678

```

**使用 Java . security . secureandom 生成随机数；**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// A Java program to demonstrate secure
// random number generation
// using java.security.SecureRandom
import java.security.SecureRandom;

public class generateRandom {

    public static void main(String args[])
    {
        // create instance of SecureRandom class
        SecureRandom rand = new SecureRandom();

        // Generate random integers in range 0 to 999
        int rand_int1 = rand.nextInt(1000);
        int rand_int2 = rand.nextInt(1000);

        // Print random integers
        System.out.println("Random Integers: " + rand_int1);
        System.out.println("Random Integers: " + rand_int2);
    }
}
```

**输出:**

```java
Random Integers: 817
Random Integers: 500

```

本文由 [**Saket Kumar**](https://www.facebook.com/saketkumar95) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。