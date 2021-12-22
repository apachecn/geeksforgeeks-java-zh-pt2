# Java 中的 URL getAuthority()方法，带示例

> 原文:[https://www . geesforgeks . org/URL-getauthority-method-in-Java-with-examples/](https://www.geeksforgeeks.org/url-getauthority-method-in-java-with-examples/)

**getAuthority()** 函数是 [URL 类](https://www.geeksforgeeks.org/url-class-java-examples/)的一部分。函数 getAuthority()返回指定网址的权限。网址的授权部分是主机名和网址的端口。

**功能签名**

```java
public String getAuthority()

```

**语法**

```java
url.getAuthority()

```

**参数**:该功能不需要任何参数

**返回类型**:函数返回**字符串**类型

下面程序说明了 getHost()函数的使用:

**例 1:**

```java
// Java program to show the
// use of the function getAuthority()

import java.net.*;

class Solution {
    public static void main(String args[])
    {

        // url  object
        URL url = null;

        try {
            // create a URL
            url
                = new URL("https:// www.geeksforgeeks.org");

            // get the Authority
            String authority
                = url.getAuthority();

            // display the URL
            System.out.println("URL = "
                               + url);

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

**Output:**

```java
URL = https:// www.geeksforgeeks.org
Authority =  www.geeksforgeeks.org

```

**示例 2:**getAuthority()和 getHost()函数的区别在于 getAuthority()返回主机和端口，而 getHost()只返回主机名。

```java
// Java program to show the
// use of the function getAuthority()

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
                    "https:// www.geeksforgeeks.org:80/url-samefile-method-in-java-with-examples/");

            // get the Authority
            String authority
                = url.getAuthority();

            // get the Host
            String host = url.getHost();

            // display the URL
            System.out.println("URL = " + url);

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

**Output:**

```java
URL = https:// www.geeksforgeeks.org:80/url-samefile-method-in-java-with-examples/
Authority =  www.geeksforgeeks.org:80
Host =  www.geeksforgeeks.org

```