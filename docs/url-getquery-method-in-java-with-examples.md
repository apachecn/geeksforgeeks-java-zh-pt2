# Java 中的 URL getQuery()方法，带示例

> 原文:[https://www . geesforgeks . org/URL-getquery-method-in-Java-with-examples/](https://www.geeksforgeeks.org/url-getquery-method-in-java-with-examples/)

**getQuery()** 功能是 **[URL 类](https://www.geeksforgeeks.org/url-class-java-examples/)** 的一部分。函数 getQuery()返回指定网址的查询。

**功能签名**:

```java
public String getQuery()
```

**语法**:

```java
url.getQuery()
```

**参数**:该功能不需要任何参数

**返回类型:**函数返回指定网址的字符串类型查询。

下面程序说明了 getQuery()函数的使用:

**示例 1** :给定一个 URL，我们将使用 getQuery()函数获取查询。

```java
// Java program to show the use
// of the function getQuery()

import java.net.*;

class Solution {
    public static void main(String args[])
    {
        // url  object
        URL url = null;

        try {
            // create a URL
            url
                = new URL(
                    "https:// www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples?title=protocol");

            // get the  Query
            String _Query = url.getQuery();

            // display the URL
            System.out.println("URL = " + url);

            // display the  Query
            System.out.println(" Query=" + _Query);
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

```java
URL = https:// www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples?title=protocol
 Query=title=protocol

```

**例 2** :现在我们不提供任何查询，使用函数获取查询并查看结果。

```java
// Java program to show the use
// of the function getQuery()

import java.net.*;

class Solution {
    public static void main(String args[])
    {
        // url  object
        URL url = null;

        try {

            // create a URL
            url = new URL(
                "https:// www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples");

            // get the  Query
            String _Query = url.getQuery();

            // display the URL
            System.out.println("URL = " + url);

            // display the  Query
            System.out.println(" Query=" + _Query);
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

```java
URL = https:// www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples
 Query=null

```