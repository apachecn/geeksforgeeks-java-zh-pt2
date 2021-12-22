# 互联网上使用 Java 的文件大小

> 原文:[https://www . geeksforgeeks . org/互联网文件大小-使用-java/](https://www.geeksforgeeks.org/size-of-file-on-the-internet-using-java/)

要从服务器获取文件的大小，首先需要使用 **URL** 和**http 连接**类连接到服务器。为了得到文件的大小，我们使用 **getContentLength()** 方法。由于文件的大小可能太大，我们使用**大整数**类。您不能使用整数数据类型，因为如果文件大于 2Gb，它会产生错误。
了解更多 **BigInteger 类**参考链接:[Java 中的 BigInteger 类](https://www.geeksforgeeks.org/biginteger-class-in-java/)
对于 **HttpURLConnection** 参考链接: [Java 中的 Java.net.HttpURLConnection 类](https://www.geeksforgeeks.org/java-net-httpurlconnection-class-java/)

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to calculate Size
// of a file on the Internet.
import java.math.BigInteger;
import java.net.URL;
import java.net.HttpURLConnection;

public class SizeFile {

    public static void main(String args[]) throws Exception
    {
        BigInteger size = new BigInteger("1");

        // get the url of web page
        URL url = new URL(
            "https://media.geeksforgeeks.org/wp-content/uploads/GATE.pdf");

        // create a connection
        HttpURLConnection conn;
        try
        {

            // open stream to get size of page
            conn = (HttpURLConnection)url.openConnection();

            // set request method.
            conn.setRequestMethod("HEAD");

            // get the input stream of process
            conn.getInputStream();

            // store size of file
            size = BigInteger.valueOf(conn.getContentLength());

            // print the size of downloaded file
            System.out.println("The Size of file is:" +
                                       size + " bytes");
            conn.getInputStream().close();
        }
        catch (Exception e)
        {
            System.out.println("Connection failed");
        }
    }
}
```