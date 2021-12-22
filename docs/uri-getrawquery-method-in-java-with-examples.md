# Java 中的 URI getRawQuery()方法，带示例

> 原文:[https://www . geesforgeks . org/uri-getrawquery-method-in-Java-with-examples/](https://www.geeksforgeeks.org/uri-getrawquery-method-in-java-with-examples/)

getRawQuery()函数是 URI 类的一部分。函数 getRawQuery()返回指定 URI 的原始查询。该函数返回查询的精确值，而不解码转义八位字节序列(如果有)。

**功能签名**:

```
public String getRawQuery()
```

**语法**:

```
uri.getRawQuery()
```

**参数:**该函数不需要任何参数
**返回类型:**该函数返回字符串类型

下面的程序说明了 getRawQuery()函数的使用:

**示例 1:** 给定一个 URI，我们将使用 getRawQuery()函数获得原始查询。

```
// Java program to show the 
// use of the function getRawQuery()

import java.net.*;

class Solution {
    public static void main(String args[])
    {
        // uri  object
        URI uri = null;

        try {
            // create a URI
            uri = new URI("https://www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples?title=protocol");

            // get the  Query
            String Raw_Query = uri.getRawQuery();

            // display the URL
            System.out.println("URI = " + uri);

            // display the  Raw Query
            System.out.println(" Raw Query=" + Raw_Query);
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
URI = https://www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples?title=protocol
 Raw Query=title=protocol

```

**例 2:** 现在我们不提供任何查询，使用函数获取查询并查看结果。

```
// Java program to show the 
// use of the function getRawQuery()

import java.net.*;

class Solution {
    public static void main(String args[])
    {
        // uri  object
        URI uri = null;

        try {
            // create a URI
            uri = new URI("https://www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples");

            // get the  Query
            String Raw_Query = uri.getRawQuery();

            // display the URL
            System.out.println("URI = " + uri);

            // display the  Raw Query
            System.out.println(" Raw Query=" + Raw_Query);
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
URI = https://www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples
 Raw Query=null

```

**示例 3:**getQuery()和 getRawQuery()返回的值是相同的，只是转义八位字节的所有序列都被解码。getRawPath()返回用户提供的字符串的确切值，但是 getQuery()函数解码转义八位字节序列(如果有)。

```
// Java program to show the 
// use of the function getRawQuery()

import java.net.*;

class Solution {
    public static void main(String args[])
    {
        // uri  object
        URI uri = null;

        try {
            // create a URI
            uri = new URI("https://www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples?title=protocol%E2%82%AC");

            // get the  Query
            String _Query = uri.getQuery();

            // display the URL
            System.out.println("URI = " + uri);

            // display the  Query
            System.out.println(" Query=" + _Query);

            // get the  Raw Query
            String Raw_Query = uri.getRawQuery();

            // display the Raw Query
            System.out.println(" Raw Query=" + Raw_Query);
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
URI = https://www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples?title=protocol%E2%82%AC
 Query=title=protocol?
 Raw Query=title=protocol%E2%82%AC

```