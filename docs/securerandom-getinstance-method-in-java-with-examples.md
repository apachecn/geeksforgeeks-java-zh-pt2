# Java 中的 SecureRandom getInstance()方法，带示例

> 原文:[https://www . geesforgeks . org/secureandom-getinstance-method-in-Java-with-examples/](https://www.geeksforgeeks.org/securerandom-getinstance-method-in-java-with-examples/)

### 字符串算法

**Java . security . SecureRandom**类的 **getInstance()** 方法用于返回实现指定随机数生成器(RNG)算法的 secureandom 对象。

此方法遍历注册的安全提供程序列表，从最首选的提供程序开始。返回一个新的安全对象，该对象封装了来自第一个支持指定算法的提供程序的安全对象。

**语法:**

```java
public static SecureRandom 
getInstance( String algorithm ) 
throws NoSuchAlgorithmException
```

**参数:**该方法以**标准 RNG 算法**为参数。

**返回值:**这个方法返回新的 **SecureRandom** 对象。

**异常:**如果没有提供程序支持指定算法的 SecureRandomSpi 实现，此方法将引发**nosuchalgorithm 异常**。

**注:**

1.  这些程序不会在联机集成开发环境中运行。
2.  每次安全随机类都会产生随机输出。

以下是说明 **getInstance()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// nextBytes() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of SecureRandom and getting instance
            // By using getInstance() method
            SecureRandom sr = SecureRandom.getInstance("SHA1PRNG");

            // Declaring the string variable
            String str = "Tajmahal";

            // Declaring the byte Array
            // converting string into byte
            byte[] b = str.getBytes();

            // printing the byte array
            System.out.println("Byte array before operation : "
                               + Arrays.toString(b));

            // generating user-specified number of random bytes
            // using nextBytes() method
            sr.nextBytes(b);

            // printing the new byte array
            System.out.println("Byte array after operation : "
                               + Arrays.toString(b));
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

```java
Byte array before operation : [84, 97, 106, 109, 97, 104, 97, 108]
Byte array after operation : [124, -66, -62, -5, -71, -4, 30, 16]
```

**例 2:**

```java
// Java program to demonstrate
// getInstance() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of SecureRandom and getting instance
            // By using getInstance() method
            System.out.println("Trying to get the instance of TAJMAHAL");
            SecureRandom sr = SecureRandom.getInstance("TAJMAHAL");

            // Declaring the string variable
            String str = "Tajmahal";

            // Declaring the byte Array
            // converting string into byte
            byte[] b = str.getBytes();

            // printing the byte array
            System.out.println("Byte array before operation : "
                               + Arrays.toString(b));

            // generating user-specified number of random bytes
            // using nextBytes() method
            sr.nextBytes(b);

            // printing the new byte array
            System.out.println("Byte array after operation : "
                               + Arrays.toString(b));
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

```java
Trying to get the instance of TAJMAHAL
Exception thrown : java.security.NoSuchAlgorithmException: TAJMAHAL SecureRandom not available
```

### getInstance(字符串算法，提供程序提供程序)

**Java . security . SecureRandom**类的 **getInstance()** 方法用于返回实现指定随机数生成器(RNG)算法的 secureandom 对象。
返回一个新的安全对象，该对象封装了来自指定提供程序对象的安全对象接口实现。请注意，指定的提供程序对象不必在提供程序列表中注册。

返回的安全对象尚未植入。若要为返回的对象设定种子，请调用 setSeed 方法。如果不调用 setSeed，对 nextBytes 的第一次调用将强制 SecureRandom 对象对自身进行种子化。如果之前调用了 setSeed，则不会发生这种自播种。

**语法:**

```java
public static SecureRandom 
getInstance( String algorithm, Provider provider )
throws NoSuchAlgorithmException
```

**参数:**该方法将以下参数作为参数

*   **算法–**RNG 算法的名称。
*   **提供商–**提供商。

**返回值:**该方法返回**新的 SecureRandom 对象**。

**异常:**该方法抛出以下异常

*   **no suchalgorithm exception–**如果指定的提供程序对象中没有指定算法的 SecureRandomSpi 实现，则为。
*   **IllegalArgumentException –** if the specified provider is null.

    **注:**

    1.  这些程序不会在联机集成开发环境中运行。
    2.  每次安全随机类都会产生随机输出。

    以下是说明 *getInstance()* 方法的示例:

    **例 1:**

    ```java
    // Java program to demonstrate
    // getInstance() method

    import java.security.*;
    import java.util.*;

    public class GFG1 {
        public static void main(String[] argv)
        {
            try {
                // creating SecureRandom object
                SecureRandom sr1 = new SecureRandom(new byte[] { 1, 2, 3, 4 });

                // creating Provider object
                Provider pd = sr1.getProvider();

                // creating the object of SecureRandom and getting instance
                // By using getInstance() method

                SecureRandom sr = SecureRandom.getInstance("SHA1PRNG", pd);

                // Declaring the string variable
                String str = "Tajmahal";

                // Declaring the byte Array
                // converting string into byte
                byte[] b = str.getBytes();

                // printing the byte array
                System.out.println("Byte array before operation : "
                                   + Arrays.toString(b));

                // generating user-specified number of random bytes
                // using nextBytes() method
                sr.nextBytes(b);

                // printing the new byte array
                System.out.println("Byte array after operation : "
                                   + Arrays.toString(b));
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

    ```java
    Byte array before operation : [84, 97, 106, 109, 97, 104, 97, 108]
    Byte array after operation : [109, 55, 116, -15, -83, 126, -128, 88]
    ```

    **注意:**以下程序在联机 IDE 中产生以下异常
    抛出异常:Java . security . providerexception:init 失败

    **例 2:**

    ```java
    // Java program to demonstrate
    // getInstance() method

    import java.security.*;
    import java.util.*;

    public class GFG1 {
        public static void main(String[] argv)
        {
            try {
                // creating SecureRandom object
                SecureRandom sr1 = new SecureRandom(new byte[] { 1, 2, 3, 4 });

                // creating Provider object
                Provider pd = sr1.getProvider();

                // creating the object of SecureRandom and getting instance
                // By using getInstance() method
                System.out.println("Trying to getting the instance of TAJMAHAL ");
                SecureRandom sr = SecureRandom.getInstance("TAJMAHAL", pd);

                // Declaring the string variable
                String str = "Tajmahal";

                // Declaring the byte Array
                // converting string into byte
                byte[] b = str.getBytes();

                // printing the byte array
                System.out.println("Byte array before operation : "
                                   + Arrays.toString(b));

                // generating user-specified number of random bytes
                // using nextBytes() method
                sr.nextBytes(b);

                // printing the new byte array
                System.out.println("Byte array after operation : "
                                   + Arrays.toString(b));
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

    ```java
    Trying to getting the instance of TAJMAHAL
    Exception thrown : java.security.NoSuchAlgorithmException: no such algorithm: TAJMAHAL for provider SUN
    ```

    ### getInstance(字符串算法，字符串提供程序)

    **Java . security . SecureRandom**类的 **getInstance()** 方法用于返回实现指定随机数生成器(RNG)算法的 secureandom 对象。

    返回一个新的安全对象，该对象封装了来自指定提供程序的安全对象接口实现。指定的提供程序必须在安全提供程序列表中注册。

    **语法:**

    ```java
    public static SecureRandom 
    getInstance( String algorithm, String provider )
    throws NoSuchAlgorithmException, NoSuchProviderException
    ```

    **参数:**该方法将以下参数作为参数

    *   **算法**–RNG 算法的名称。有关标准 RNG 算法名称的信息，请参见 Java 加密体系结构标准算法名称文档中的安全域部分。
    *   **提供者–**提供者的名称。

    **返回值:**该方法返回**新的 SecureRandom 对象**。

    **异常:**该方法抛出以下异常

    *   **no suchalgorithm exception**–如果指定的提供程序无法提供指定算法的 SecureRandomSpi 实现。
    *   **NoSuchProviderException**–如果指定的提供商未在安全提供商列表中注册。
    *   **IllegalArgumentException**–如果提供程序名称为空。

    **注:**

    1.  这些程序不会在联机集成开发环境中运行。
    2.  每次安全随机类都会产生随机输出。

    以下是说明 *getInstance()* 方法的示例:

    **例 1:**

    ```java
    // Java program to demonstrate
    // getInstance() method

    import java.security.*;
    import java.util.*;

    public class GFG1 {
        public static void
            main(String[] argv)
                throws NoSuchAlgorithmException,
                       NoSuchProviderException
        {
            try {
                // creating SecureRandom object
                SecureRandom sr1 = new SecureRandom(new byte[] { 1, 2, 3, 4 });

                // creating Provider object
                Provider pd = sr1.getProvider();

                // getting provider name
                // by using method getname()
                String provider = pd.getName();

                // getting algorithm name
                // by using     getAlgorithm() mathod
                String algo = sr1.getAlgorithm();

                // creating the object of SecureRandom and getting instance
                // By using getInstance() method
                SecureRandom sr = SecureRandom.getInstance(algo, provider);

                // Declaring the string variable
                String str = "Tajmahal";

                // Declaring the byte Array
                // converting string into byte
                byte[] b = str.getBytes();

                // printing the byte array
                System.out.println("Byte array before operation : "
                                   + Arrays.toString(b));

                // generating user-specified number of random bytes
                // using nextBytes() method
                sr.nextBytes(b);

                // printing the new byte array
                System.out.println("Byte array after operation : "
                                   + Arrays.toString(b));
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

    ```java
    Byte array before operation : [84, 97, 106, 109, 97, 104, 97, 108]
    Byte array after operation : [-11, 81, 39, 67, -95, -51, 115, -18]
    ```

    **例 2:**

    ```java
    // Java program to demonstrate
    // getInstance() method

    import java.security.*;
    import java.util.*;

    public class GFG1 {
        public static void
            main(String[] argv)
                throws NoSuchAlgorithmException,
                       NoSuchProviderException
        {
            try {
                // creating SecureRandom object
                SecureRandom sr1 = new SecureRandom(new byte[] { 1, 2, 3, 4 });

                // creating Provider object
                Provider pd = sr1.getProvider();

                // getting provider name
                // by using method getname()
                String provider = pd.getName();

                // creating the object of SecureRandom and getting instance
                // By using getInstance() method
                System.out.println("Trying to take TAJMAHAL as a algorithm");
                SecureRandom sr = SecureRandom.getInstance("TAJMAHAL", provider);

                // Declaring the string variable
                String str = "Tajmahal";

                // Declaring the byte Array
                // converting string into byte
                byte[] b = str.getBytes();

                // printing the byte array
                System.out.println("Byte array before operation : "
                                   + Arrays.toString(b));

                // generating user-specified number of random bytes
                // using nextBytes() method
                sr.nextBytes(b);

                // printing the new byte array
                System.out.println("Byte array after operation : "
                                   + Arrays.toString(b));
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

    ```java
    Trying to take TAJMAHAL as a algorithm
    Exception thrown : java.security.NoSuchAlgorithmException: no such algorithm: TAJMAHAL for provider SUN
    ```

    **例 3:**

    ```java
    // Java program to demonstrate
    // getInstance() method

    import java.security.*;
    import java.util.*;

    public class GFG1 {
        public static void
            main(String[] argv)
                throws NoSuchAlgorithmException,
                       NoSuchProviderException
        {
            try {
                // creating SecureRandom object
                SecureRandom sr1 = new SecureRandom(new byte[] { 1, 2, 3, 4 });

                // getting algorithm name
                // by using     getAlgorithm() mathod
                String algo = sr1.getAlgorithm();

                // creating the object of SecureRandom and getting instance
                // By using getInstance() method
                System.out.println("Trying to taking MOON as a provider");
                SecureRandom sr = SecureRandom.getInstance(algo, "MOON");

                // Declaring the string variable
                String str = "Tajmahal";

                // Declaring the byte Array
                // converting string into byte
                byte[] b = str.getBytes();

                // printing the byte array
                System.out.println("Byte array before operation : "
                                   + Arrays.toString(b));

                // generating user-specified number of random bytes
                // using nextBytes() method
                sr.nextBytes(b);

                // printing the new byte array
                System.out.println("Byte array after operation : "
                                   + Arrays.toString(b));
            }

            catch (NoSuchAlgorithmException e) {

                System.out.println("Exception thrown : " + e);
            }
            catch (NoSuchProviderException e) {

                System.out.println("Exception thrown : " + e);
            }
        }
    }
    ```

    **输出:**

    ```java
    Trying to taking MOON as a provider
    Exception thrown : java.security.NoSuchProviderException: no such provider: MOON
    ```