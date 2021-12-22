# Java 中使用 Base64 的 URL 编码/解码

> 原文:[https://www . geesforgeks . org/URL-编码-解码-使用-base64-in-java/](https://www.geeksforgeeks.org/url-encoding-decoding-using-base64-in-java/)

Base 64 是一种编码方案，它将二进制数据转换成文本格式，这样编码的文本数据可以很容易地在网络上传输而不被破坏，并且没有任何数据丢失。[(基本 64 格式参考)](https://www.geeksforgeeks.org/encode-ascii-string-base-64-format/)。

网址编码与基本编码相同，唯一的区别是它编码或解码网址和文件名安全的 Base64 字母表，并且不添加任何行分隔。

**网址编码**

```java
String encodedURL = Base64.getUrlEncoder()
                       .encodeToString(actualURL_String.getBytes());

```

**解释:**在上面的代码中我们称之为 Base64。使用 getUrlEncoder()进行编码，然后通过将 encodeToString()方法中实际 URL 的字节值作为参数传递来获取编码后的 URLstring。

**网址解码**

```java
byte[] decodedURLBytes = Base64.getUrlDecoder().decode(encodedURLString);

String actualURL= new String(decodedURLBytes);

```

**解释:**在上面的代码中我们称之为 Base64。解码器使用 getUrlDecoder()然后解码在 decode()方法中作为参数传递的 URL 字符串，然后将返回值转换为实际的 URL。

下面的程序说明了用 Java 编码和解码网址:

**程序 1:** 使用 Base64 类的 URL 编码。

```java
// Java program to demonstrate
// URL encoding using Base64 class

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {
        // create a sample url String to encode
        String sampleURL = "https:// www.geeksforgeeks.org/";

        // print actual URL String
        System.out.println("Sample URL:\n"
                           + sampleURL);

        // Encode into Base64 URL format
        String encodedURL = Base64.getUrlEncoder()
                                .encodeToString(sampleURL.getBytes());

        // print encoded URL
        System.out.println("encoded URL:\n"
                           + encodedURL);
    }
}
```

**Output:**

```java
Sample URL:
https://www.geeksforgeeks.org/
encoded URL:
aHR0cHM6Ly93d3cuZ2Vla3Nmb3JnZWVrcy5vcmcv

```

**程序 2:** 使用 Base64 类进行 URL 解码。

```java
// Java program to demonstrate
// Decoding Basic Base 64 format to String

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {
        // create a encoded URL to decode
        String encoded = "aHR0cHM6Ly93d3cuZ2Vla3Nmb3JnZWVrcy5vcmcv";

        // print encoded URL
        System.out.println("encoded URL:\n"
                           + encoded);

        // decode into String URL from encoded format
        byte[] actualByte = Base64.getUrlDecoder()
                                .decode(encoded);

        String actualURLString = new String(actualByte);

        // print actual String
        System.out.println("actual String:\n"
                           + actualURLString);
    }
}
```

**Output:**

```java
encoded URL:
aHR0cHM6Ly93d3cuZ2Vla3Nmb3JnZWVrcy5vcmcv
actual String:
https://www.geeksforgeeks.org/

```

**参考文献:**

*   [https://docs . Oracle . com/javae/10/docs/API/Java/util/base 64 . html](https://docs.oracle.com/javase/10/docs/api/java/util/Base64.html)
*   [https://www . geesforgeks . org/decode-encoded-base-64-string-ascii-string/](https://www.geeksforgeeks.org/decode-encoded-base-64-string-ascii-string/)
*   [https://www . geesforgeks . org/encode-ascii-string-base-64-format/](https://www.geeksforgeeks.org/encode-ascii-string-base-64-format/)