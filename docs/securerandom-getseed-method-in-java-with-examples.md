# Java 中的 SecureRandom getSeed()方法，带示例

> 原文:[https://www . geesforgeks . org/secureandom-getseed-method-in-Java-with-examples/](https://www.geeksforgeeks.org/securerandom-getseed-method-in-java-with-examples/)

**Java . security . secureandom**类的 **getSeed()** 方法用于返回给定的种子字节数，该字节数是使用该类用来给自身播种的种子生成算法计算的。此调用可用于播种其他随机数生成器。

包含此方法只是为了向后兼容。我们鼓励调用者使用可选的 getInstance 方法之一来获取一个 SecureRandom 对象，然后调用 generateSeed 方法从该对象中获取种子字节。

**语法:**

```
public static byte[] getSeed(int numBytes)
```

**参数:**该方法以种子字节数为参数进行生成。

**返回值:**该方法返回种子字节。

以下是说明 getSeed()方法的示例:

**实施例 1:**

```
// Java program to demonstrate
// getSeed() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of SecureRandom
            SecureRandom sr = SecureRandom.getInstance("SHA1PRNG");

            // getting the Provider of the SecureRandom sr
            // by using method getSeed()
            byte[] bb = sr.getSeed(5);

            // printing the byte array
            System.out.println("Seed Bytes : " + Arrays.toString(bb));
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```
Seed Bytes : [1, 2, 3, 4, 1]
```

**实施例 2:**

```
// Java program to demonstrate
// getSeed() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of SecureRandom
            SecureRandom sr = SecureRandom.getInstance("SHA1PRNG");

            // getting the Provider of the SecureRandom sr
            // by using method getSeed()
            byte[] bb = sr.getSeed(10);

            // printing the byte array
            System.out.println("Seed Bytes : " + Arrays.toString(bb));
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (ProviderException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```
Seed Bytes : [-64, 79, 82, -118, -97, -95, -80, -101, -40, 12]
```

**注:**

1.  上述程序不会在联机 IDE 上运行。
2.  每次安全随机类都会产生随机输出。