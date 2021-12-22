# Java 中的 URI getAuthority()方法，带示例

> 原文:[https://www . geesforgeks . org/uri-getauthority-method-in-Java-with-examples/](https://www.geeksforgeeks.org/uri-getauthority-method-in-java-with-examples/)

**getAuthority()** 函数是 URI 类的一部分。函数 getAuthority()返回指定 URI 的权限。网址的权威部分是 URI 的主机名和端口。

**功能签名**

```
public String getAuthority()
```

**语法** :

```
url.getAuthority()
```

**参数**该功能不需要任何参数

**返回类型**该函数返回**字符串类型**，这是指定网址的权限。

下面的程序说明了 getRawAuthority()函数的使用:

**例 1:**

```
// Java program to show the
// use of the function getAuthority()

import java.net.*;

class GFG {
    public static void main(String args[])
    {
        // URI  object
        URI uri = null;

        try {
            // create a URI
            uri
                = new URI(
                    "https://www.geeksforgeeks.org");

            // get the Authority
            String authority
                = uri.getAuthority();

            // display the URI
            System.out.println("URI = " + uri);

            // display the Authority
            System.out.println("Authority = "
                               + authority);
        }

        // if any error occurs
        catch (Exception e) {

            // display the error
            System.out.println(e);
        }
    }
}
```

**输出:**

```
URI = https://www.geeksforgeeks.org
Authority = www.geeksforgeeks.org

```

**示例 2:**getAuthority()和 getHost()函数的区别在于 getAuthority()返回主机和端口，而 getHost()只返回主机名。

```
// Java program to show the
// use of the function getAuthority()

import java.net.*;

class GFG {
    public static void main(String args[])
    {
        // url  object
        URI uri = null;

        try {
            // create a URI
            uri
                = new URI(
                    "https://www.geeksforgeeks.org:80");

            // get the Authority
            String authority
                = uri.getAuthority();

            // get the Host
            String host = uri.getHost();

            // display the URI
            System.out.println("URI = " + uri);

            // display the Authority
            System.out.println("Authority = "
                               + authority);

            // display the Host
            System.out.println("Host = " + host);
        }

        // if any error occurs
        catch (Exception e) {

            // display the error
            System.out.println(e);
        }
    }
}
```

**输出:**

```
URI = https://www.geeksforgeeks.org:80
Authority = www.geeksforgeeks.org:80
Host = www.geeksforgeeks.org

```

**示例 3:**getAuthority()和 getRawAuthority()返回的值是相同的，只是转义八位字节的所有序列都被解码。getRawAuthority()返回用户提供的字符串的确切值，但是 getAuthority()函数解码转义八位字节序列(如果有)。

```
// Java program to show the
// use of the function getAuthority()

import java.net.*;

class GFG {
    public static void main(String args[])
    {
        // url  object
        URI uri = null;

        try {
            // create a URI
            uri
                = new URI(
                    "https://www.geeksforgeeks%E2%82%AC.org:80");

            // get the Authority
            String authority
                = uri.getAuthority();

            // get the Raw Authority
            String Raw_authority
                = uri.getRawAuthority();

            // display the URI
            System.out.println("URI = " + uri);

            // display the Authority
            System.out.println("Authority = "
                               + authority);

            // display the Raw Authority
            System.out.println("Raw Authority = "
                               + Raw_authority);
        }

        // if any error occurs
        catch (Exception e) {

            // display the error
            System.out.println(e);
        }
    }
}
```

**输出:**

```
URI = https://www.geeksforgeeks%E2%82%AC.org:80
Authority = www.geeksforgeeks?.org:80
Raw Authority = www.geeksforgeeks%E2%82%AC.org:80

```

]