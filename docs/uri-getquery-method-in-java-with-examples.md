# Java 中的 URI getQuery()方法，带示例

> 原文:[https://www . geesforgeks . org/uri-getquery-method-in-Java-with-examples/](https://www.geeksforgeeks.org/uri-getquery-method-in-java-with-examples/)

getQuery()函数是 URI 类的一部分。函数 getQuery()返回指定 URI 的查询。

**功能签名**

```
public String getQuery()
```

**语法**

```
uri.getQuery()
```

**参数**该功能不需要任何参数

**返回类型:**函数返回字符串类型

下面程序说明了 getQuery()函数的使用:

**示例 1:** 给定一个 URI，我们将使用 getQuery()函数获得查询。

```
// Java program to show the use of the function getQuery()

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
            String _Query = uri.getQuery();

            // display the URL
            System.out.println("URI = " + uri);

            // display the  Query
            System.out.println(" Query= " + _Query);
        }
        // if any error occurs
        catch (Exception e) {
            // display the error
            System.out.println(e);
        }
    }
}
```

**Output:**

```
URI = https://www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples?title=protocol
 Query= title=protocol

```

**例 2:** 现在我们不提供任何查询，使用函数获取查询并查看结果。

```
// Java program to show the use of the function getQuery()
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
            String _Query = uri.getQuery();

            // display the URL
            System.out.println("URI = " + uri);

            // display the  Query
            System.out.println(" Query=" + _Query);
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
 Query=null

```

**示例 3:**getQuery()和 getRawQuery()返回的值是相同的，只是转义八位字节的所有序列都被解码。
getRawPath()返回用户提供的字符串的精确值，但是 getQuery()函数解码转义八位字节序列(如果有)。

```
// Java program to show the use of the function getQuery()
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