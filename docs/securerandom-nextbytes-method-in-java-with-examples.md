# Java 中的 SecureRandom nextBytes()方法，带示例

> 原文:[https://www . geesforgeks . org/secureandom-next bytes-method-in-Java-with-examples/](https://www.geeksforgeeks.org/securerandom-nextbytes-method-in-java-with-examples/)

类的 **nextBytes()** 方法用于生成用户指定的随机字节数。

如果之前没有调用过 setSeed，那么对该方法的第一次调用会强制该 SecureRandom 对象对自身进行种子化。如果之前调用了 setSeed，则不会发生这种自播种。

**语法:**

```
public void nextBytes(byte[] bytes)
```

**参数:**该方法以随机字节填充的数组为参数。

**注:**

1.  这些程序不会在联机集成开发环境中运行。
2.  每次安全随机类都会产生随机输出。

以下是说明 *nextBytes()* 方法的示例:

**例 1:**

```
// Java program to demonstrate
// nextBytes() method

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

            // Declaring the byte Array
            // converting string into byte
            byte[] b = str.getBytes();

            // printing the byte array
            System.out.println("Byte array before operation : " + Arrays.toString(b));

            // generating user-specified number of random bytes
            // using nextBytes() method
            sr.nextBytes(b);

            // printing the new byte array
            System.out.println("Byte array after operation : " + Arrays.toString(b));
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
Byte array before operation : [84, 97, 106, 109, 97, 104, 97, 108]
Byte array after operation : [-79, -110, -18, -31, -54, -36, 63, -61]
```

**注意:**以下程序在 GeeksForGeeks IDE 上抛出以下异常，但它将在任何命令提示符下高效运行(JDK)

```
Exception thrown : java.security.ProviderException: init failed
```

**例 2:**

```
// Java program to demonstrate
// nextBytes() method

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

            // printing the byte array
            System.out.println("Byte array before operation : " + Arrays.toString(b));

            // generating user-specified number of random bytes
            // using nextBytes() method
            sr.nextBytes(b);

            // printing the new byte array
            System.out.println("Byte array after operation : " + Arrays.toString(b));
        }

        catch (ProviderException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```
Byte array before operation : [84, 97, 106, 109, 97, 104, 97, 108]
Byte array after operation : [-14, 77, 123, 121, 116, 50, -89, -86]
```