# Java 中的 URI getHost()方法，带示例

> 原文:[https://www . geesforgeks . org/uri-gethost-method-in-Java-with-examples/](https://www.geeksforgeeks.org/uri-gethost-method-in-java-with-examples/)

getHost()函数是 URI 类的一部分。函数 getHost()返回指定 URI 的主机。
URL 的主机部分是 URI 的主机名。

**功能签名**:

```java
public String getHost()
```

**返回类型**函数返回字符串类型

**语法**

```java
url.getHost()
```

**参数**:该功能不需要任何参数

**以下程序将说明 getHost()功能的使用**

**例 1:**

```java
// Java program to show the 
// use of the function getHost()

import java.net.*;
class Solution {
public static void main(String args[])
    {
        // URI  object
        URI uri = null;

        try {
            // create a URI
            uri = new URI("https://www.geeksforgeeks.org");

            // get the Host
            String host = uri.getHost();

            // display the URI
            System.out.println("URI = " + uri);

            // display the Host
            System.out.println("Host = " + host);
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

```java
URI = https://www.geeksforgeeks.org
Host = www.geeksforgeeks.org

```

**示例 2:**getAuthority()和 getHost()函数的区别在于 getAuthority()返回主机和端口，而 getHost()只返回主机名。

```java
// Java program to show the 
// use of the function getHost()

import java.net.*;

class Solution {
    public static void main(String args[])
    {
        // url  object
        URI uri = null;

        try {
            // create a URI
            uri = new URI("https://www.geeksforgeeks.org:80");

            // get the Authority
            String authority = uri.getAuthority();

            // get the Host
            String host = uri.getHost();

            // display the URI
            System.out.println("URI = " + uri);

            // display the Authority
            System.out.println("Authority = " + authority);

            // display the Host
            System.out.println("Host = " + host);
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

```java
URI = https://www.geeksforgeeks.org:80
Authority = www.geeksforgeeks.org:80
Host = www.geeksforgeeks.org

```