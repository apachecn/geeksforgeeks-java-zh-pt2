# Java 中的 URL getRef()方法，带示例

> 原文:[https://www . geesforgeks . org/URL-getref-method-in-Java-with-examples/](https://www.geeksforgeeks.org/url-getref-method-in-java-with-examples/)

**getRef()** 函数是 URL 类的一部分。函数 getRef()返回指定网址的引用或锚点部分。

**功能签名**:

```java
public String getRef()
```

**语法**:

```java
url.getRef()
```

**参数:**该功能不需要任何参数

**返回类型:**函数返回字符串类型

以下程序说明了 getRef()函数的使用:

**示例 1** :给定一个 URL，我们将使用 getRef()函数获取引用或锚点。

```java
// Java program to show the
// use of the function getRef()

import java.net.*;

class Solution {
    public static void main(String args[])
    {
        // url  object
        URL url = null;

        try {

            // create a URL
            url= new URL("https:// www.geeksforgeeks.org#Arnab_Kundu");

            // get the  Reference or anchor
            String _Ref=url.getRef();

            // display the URL
            System.out.println("URL = "+url);

            // display the  Reference or anchor
            System.out.println(" Reference or anchor="+_Ref);
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
URL = https:// www.geeksforgeeks.org#Arnab_Kundu
 Reference or anchor=Arnab_Kundu

```

**例 2** :现在我们不提供任何锚点，使用函数获取 Reference 或者 anchor，看结果。

```java
// Java program to show the
// use of the function getRef()

import java.net.*;

class Solution {
    public static void main(String args[])
    {
        // url  object
        URL url = null;

        try {

            // create a URL
            url = new URL("https:// www.geeksforgeeks.org");

            // get the  Reference or anchor
            String _Ref = url.getRef();

            // display the URL
            System.out.println("URL = " + url);

            // display the  Reference or anchor
            System.out.println(" Reference or anchor= "
                               + _Ref);
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
 Reference or anchor= null

```