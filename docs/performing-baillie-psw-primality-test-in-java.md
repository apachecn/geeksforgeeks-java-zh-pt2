# 在 Java 中执行白利-PSW 素性测试

> 原文:[https://www . geesforgeks . org/performing-bail lie-PSW-primality-test-in-Java/](https://www.geeksforgeeks.org/performing-baillie-psw-primality-test-in-java/)

Baillie PSW 素性测试通常是一种概率素性测试算法，试图定义给定的数是复合的还是可能的素性，它是以罗伯特·Baillie 的名字命名的。这个检验是由 Baillie 和瓦格斯塔夫(1980)和 pomeranse(1980 和 1984)基于强伪素数和 Lucas 伪素数提出的。一个令人震惊的事实是，波美拉尼斯最初宣布，任何人发现一个可以通过这一测试的复合数，奖金为 30 美元，这一奖金后来提高到 620 美元。有趣的是，还没有复合数通过这个测试的例子，截止到 2009 年 6 月 13 日，杰夫·吉尔克里斯特宣布 10^(17).没有 Baillie-PSW 伪素数但是，**椭圆曲线素性程序** PRIMO 用这个测试检查所有中间可能的素，以防万一如果有任何可能的复合数，这个认证会失败，这从来没有发生过，PRIMO 程序作者 M. Martin 自信地估计，没有一个少于 10000 位数的复合数可以欺骗这个已经存在的测试。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to implement Baillie - PSW Primality test
// Importing utility classes
import java.util.Scanner;
import java.util.Random;

// Class FermatPrimality
public class GFG {

    // Method 1
    // To check if prime or not
    public boolean isPrime(long n, int iteration) {

        // Base case
        if (n == 0 || n == 1)
            return false;

        // Base case 2
        //  is prime
        if (n == 2)
            return true;

        // An even number other than 2 is composite
        if (n % 2 == 0)
            return false;

        // Creating object of Random class
        Random rand = new Random();
        for (int i = 0; i < iteration; i++) {

            // Getting positive valuee using absolute function
            // of Math class
            long r = Math.abs(rand.nextLong());
            long a = r % (n - 1) + 1;
            if (modPow(a, n - 1, n) != 1)
                return false;
        }
        return true;
    }

    // Method 2
    // To calculate (a ^ b) % c
    public long modPow(long a, long b, long c) {

        // Initially declaring and initializing the long variable
        // to unity
        long res = 1;
        for (int i = 0; i < b; i++) {
            res *= a;
            res %= c;
        }
        return res % c;
    }
    // Method 3
    // Main driver method
    public static void main (String[] args) {

        // Creating object of Scanner class to take input from user
        Scanner scan = new Scanner(System.in);

        // Display message only
        System.out.println("Fermat Primality Algorithm Test\n");

        // Make an object of GFG class
        GFG fp = new GFG();

        // Display message only
        System.out.println("Enter number\n");

        // Accepting the number using nextLong() method
        long num = scan.nextLong();

        // Display message only
        System.out.println("\nEnter number of iterations");

        // Accepting number of iterations using nextInt() method
        int k = scan.nextInt();

        // Check if prime
        boolean prime = fp.isPrime(num, k);
        if (prime)
            System.out.println("\n" + num + " is prime");
        else
            System.out.println("\n" + num + " is composite");
    }
}
```

**输出:**

![](img/8e64a016a0a9813b40e12108b270f556.png)

**输出说明:**

首先，我们构造了一个方法 isPrime()来寻找给定的数是否是素数。我们创建了一个方法 modPow()，用于寻找模数来计算 isPrime()方法的逻辑。我们从用户那里获取输入，并应用函数 isPrime()，作为素性测试的一部分，我们获取迭代次数。对于迭代的次数和给定的迭代次数，我们应用方法 isPrime()和 findPow()，并在成功进行 Baillie=PSW 素性测试后生成输出。无论给定的数是质数还是合成数，我们都会输出结果。