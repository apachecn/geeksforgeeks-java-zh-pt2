# Java 中 SecureRandom setSeed()方法，带示例

> 原文:[https://www . geesforgeks . org/secureandom-setseed-method-in-Java-with-examples/](https://www.geeksforgeeks.org/securerandom-setseed-method-in-java-with-examples/)

**setSeed( byte[] seed )**

**Java . security . secureandom**类的 **setSeed()** 方法用于重新播种这个随机对象。给定的种子补充而不是取代现有的种子。因此，重复调用保证永远不会降低随机性。

**语法:**

```
public void setSeed(byte[] seed)
```

**参数:**该方法以**种子**为参数。

**注意:**每次安全随机类都会产生随机输出

以下是说明*设置种子()*方法的示例:

**例 1:**

```
// Java program to demonstrate
// setSeed() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of SecureRandom
            SecureRandom sr = SecureRandom.getInstance("SHA1PRNG");

            // Declaring the string variable
            String str = "Tajmahal";

            // Declaring the byte Array b
            byte[] b = str.getBytes();

            // Reseeding the random object
            sr.setSeed(b);

            // getting the seeds
            byte[] seeds = sr.getSeed(10);

            // printing the seed serialwise
            for (int i = 0; i < seeds.length; i++)
                System.out.println("Seed[" + i + "] : " + seeds[i]);
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
Seed[0]:69
Seed[0] : 23
Seed[1] : -99
Seed[2] : -51
Seed[3] : 107
Seed[4] : 41
Seed[5] : -96
Seed[6] : -93
Seed[7] : -86
Seed[8] : 127
Seed[9] : 47

```

**例 2:**

```
// Java program to demonstrate
// setSeed() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of SecureRandom
            SecureRandom sr = new SecureRandom(new byte[] { 1, 2, 3, 4 });

            // Declaring the string variable
            String str = "Tajmahal";

            // Declaring the byte Array b
            byte[] b = str.getBytes();

            // Reseeding the random object
            sr.setSeed(b);

            // getting the seeds
            byte[] seeds = sr.getSeed(10);

            // printing the seed serialwise
            for (int i = 0; i < seeds.length; i++)
                System.out.println("Seed[" + i + "]:" + seeds[i]);
        }

        catch (ProviderException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```
Seed[0]:92
Seed[1]:127
Seed[2]:28
Seed[3]:-127
Seed[4]:-100
Seed[5]:-110
Seed[6]:86
Seed[7]:-55
Seed[8]:48
Seed[9]:-78
```

**setSeed(long seed)**

**Java . security . secureandom**类的 **setSeed(长种子)**方法用于使用给定长种子中包含的八个字节重新播种这个随机对象。给定的种子补充而不是取代现有的种子。因此，重复调用保证永远不会降低随机性。

**语法:**

```
public void setSeed( long seed )
```

**参数:**该方法以**种子**为参数

**注意:**每次安全随机类都会产生随机输出

以下是说明*设置种子()*方法的示例:

**例 1:**

```
// Java program to demonstrate
// setSeed() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {
            // creating the object of SecureRandom
            SecureRandom sr = SecureRandom.getInstance("SHA1PRNG", "SUN");

            // Reseeding the random object
            sr.setSeed(101L);

            // getting the seeds
            byte[] seeds = sr.getSeed(10);

            // printing the seed serialwise
            for (int i = 0; i < seeds.length; i++)
                System.out.println("Seed[" + i + "] : " + seeds[i]);
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
Seed[0] : -36
Seed[1] : -65
Seed[2] : -94
Seed[3] : 16
Seed[4] : -104
```

**例 2:**

```
// Java program to demonstrate
// setSeed() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of SecureRandom
            SecureRandom sr = new SecureRandom(new byte[] { 1, 2, 3, 4 });

            // Reseeding the random object
            sr.setSeed(101L);

            // getting the seeds
            byte[] seeds = sr.getSeed(10);

            // printing the seed serialwise
            for (int i = 0; i < seeds.length; i++)
                System.out.println("Seed[" + i + "]:" + seeds[i]);
        }

        catch (ProviderException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```
Seed[0]:-29
Seed[1]:-93
Seed[2]:6
Seed[3]:66
Seed[4]:126
Seed[5]:93
Seed[6]:-58
Seed[7]:-91
Seed[8]:-62
Seed[9]:-58
```