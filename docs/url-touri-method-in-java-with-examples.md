# Java 中的 URL toURI()方法，带示例

> 原文:[https://www . geesforgeks . org/URL-touri-method-in-Java-with-examples/](https://www.geeksforgeeks.org/url-touri-method-in-java-with-examples/)

[URL 类](https://www.geeksforgeeks.org/url-class-java-examples/)的 **getURI()** 函数将 URL 对象转换为 URI 对象。任何用 RFC 2396 编译的网址都可以转换成 URI。不符合指定格式的网址如果转换成 URI 格式会产生错误。

**功能签名**

```java
public URI toURI()

```

**语法**

```java
url.toURI()

```

**参数:**此方法不接受任何参数。

**返回类型:**该函数返回一个 **URI 对象**，该对象由该网址对象转换而来。

**异常**:如果该网址没有严格按照 RFC2396 格式，无法转换为 URI，则该函数抛出**uri synctaxerce**。

下面的例子将说明 toURI()函数的使用:

**例 1:**

```java
// Java program to convert URL to URI

import java.net.*;

class GFG {
    public static void main(String args[])
    {

        // url and uri objects
        URL url = null;
        URI uri = null;

        try {

            // create a URL
            url = new URL("https://www.geeksforgeeks.org");

            // display the URL
            System.out.println("URL: " + url);

            // convert the URL to URI
            uri = url.toURI();

            // display the URI
            System.out.println("URI: " + uri);
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
URL: https://www.geeksforgeeks.org
URI: https://www.geeksforgeeks.org

```

**例 2:**

```java
// Java program to convert URL to URI

import java.net.*;

class GFG {
    public static void main(String args[])
    {

        // url and uri objects
        URL url = null;
        URI uri = null;

        try {

            // create an invalid URL
            url = new URL("https://www.geeksfor>geeks.com");

            // display the URL
            System.out.println("URL: " + url);

            // convert the URL to URI
            uri = url.toURI();

            // display the URI
            System.out.println("URI: " + uri);
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
URL: https:// www.geeksfor>geeks.com
java.net.URISyntaxException:
 Illegal character in authority at index 8:
 https:// www.geeksfor>geeks.com

```