# Java 中的 URI getRawPath()方法，带示例

> 原文:[https://www . geesforgeks . org/uri-getrawpath-method-in-Java-with-examples/](https://www.geeksforgeeks.org/uri-getrawpath-method-in-java-with-examples/)

函数是 URI 类的一部分。函数 getRawPath()返回指定 URI 的路径名。该函数返回路径的精确值，而不解码转义八位字节序列(如果有)。

**功能签名**:

```
public String getRawPath()
```

**语法**:

```
url.getRawPath()
```

**参数:**该函数不需要任何参数
**返回类型:**该函数返回字符串类型

下面的程序说明了 getRawPath()函数的使用:

**示例 1:** 给定一个 URI，我们将使用 getRawPath()函数获得路径。

```
// Java program to show the 
// use of the function getRawPath()

import java.net.*;

class Solution {
    public static void main(String args[])
    {
        // uri  object
        URI uri = null;

        try {
            // create a URI
            uri = new URI("https://www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples/");

            // get the  Path
            String Raw_Path = uri.getRawPath();

            // display the URI
            System.out.println("URI = " + uri);

            // display the  Raw Path
            System.out.println(" Raw Path=" + Raw_Path);
        }
        // if any error occurs
        catch (URISyntaxException e) {
            // display the error
            System.out.println("URI Exception =" + e.getMessage());
        }
    }
}
```

**Output:**

```
URI = https://www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples/
 Raw Path=/url-getprotocol-method-in-java-with-examples/

```

**示例 2:**getPath()和 getRawPath()返回的值是相同的，只是转义八位字节的所有序列都被解码。getRawPath()返回用户提供的字符串的确切值，但是 getPath()函数解码转义八位字节序列(如果有)。

```
// Java program to show the 
// use of the function getRawPath()

import java.net.*;

class Solution {
    public static void main(String args[])
    {
        // uri  object
        URI uri = null;

        try {
            // create a URI
            uri = new URI("https://www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples%E2%82%AC/");

            // get the  Path
            String _Path = uri.getPath();

            // get the  Raw Path
            String Raw_Path = uri.getRawPath();

            // display the URI
            System.out.println("URI = " + uri);

            // display the  Path
            System.out.println(" Path=" + _Path);

            // display the  Raw_Path
            System.out.println(" Raw Path=" + Raw_Path);
        }
        // if any error occurs
        catch (URISyntaxException e) {
            // display the error
            System.out.println("URI Exception =" + e.getMessage());
        }
    }
}
```

**Output:**

```
URI = https://www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples%E2%82%AC/
 Path=/url-getprotocol-method-in-java-with-examples?/
 Raw Path=/url-getprotocol-method-in-java-with-examples%E2%82%AC/

```