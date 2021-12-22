# Java 中 ExternalForm()方法的 URL，带示例

> 原文:[https://www . geesforgeks . org/URL-to externalform-in-Java-method-with-examples/](https://www.geeksforgeeks.org/url-toexternalform-method-in-java-with-examples/)

**toExternalForm()** 函数是 URL 类的一部分。函数的作用是:返回指定网址的字符串表示形式。该字符串是通过为此对象调用流协议处理程序的 toExternalForm()函数创建的。

**功能签名:**

```
public String toExternalForm()
```

**语法:**

```
url.toExternalForm()
```

**参数:**该函数不需要任何参数
**返回类型:**该函数返回字符串类型

**下面的程序说明了 toExternalForm()函数的使用:**

****示例 1** :给定一个网址，我们将对该网址进行字符串表示**

```
// Java program to show the
// use of the function toExternalForm()

import java.net.*;

class Solution {
    public static void main(String args[])
    {
        // url  object
        URL url = null;

        try {
            // create a URL
            url = new URL("https:// www.geeksforgeeks.org");

            // get the  ExternalForm
            String _ExternalForm = url.toExternalForm();

            // display the URL
            System.out.println("URL = " + url);

            // display the  ExternalForm
            System.out.println(" String representation= "
                               + _ExternalForm);
        }
        // if any error occurs
        catch (Exception e) {

            // display the error
            System.out.println(e);
        }
    }
}
```

****Output:**

```
URL = https:// www.geeksforgeeks.org
 String representation= https:// www.geeksforgeeks.org

```** 

****例 2:****

```
// Java program to show the
// use of the function toExternalForm()

import java.net.*;

class Solution {
    public static void main(String args[])
    {
        // url  object
        URL url = null;

        try {

            // create a URL
            url= new URL("https:// www.geeksforgeeks.org#Arnab_Kundu");

            // get the  ExternalForm
            String _ExternalForm = url.toExternalForm();

            // display the URL
            System.out.println("URL = " + url);

            // display the  ExternalForm
            System.out.println(" String representation= "
                               + _ExternalForm);
        }

        // if any error occurs
        catch (Exception e) {

            // display the error
            System.out.println(e);
        }
    }
}
```

****Output:**

```
URL = https:// www.geeksforgeeks.org#Arnab_Kundu
 String representation= https:// www.geeksforgeeks.org#Arnab_Kundu

```**