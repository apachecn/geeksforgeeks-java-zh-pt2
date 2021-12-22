# 使用网址连接类

读取网址

> 原文:[https://www . geesforgeks . org/reading-URL-using-URL connection-class/](https://www.geeksforgeeks.org/reading-url-using-urlconnection-class/)

在[之前的文章中，](https://www.geeksforgeeks.org/url-class-java-examples/)我们看到了如何创建一个 URL 对象，获取互联网上任何资源的信息。但是仅仅获得状态信息并不是真实世界应用的真正动机。检索信息、处理信息并将结果发送回服务器，或者只是显示从服务器检索到的所需信息，这就是我们的目标。例如，考虑一个小应用程序，它要求用户输入电影名称，然后返回电影的“imdb”评级或返回与该电影相关的所有链接。所有这些都可以通过使用 URLConnection 类来实现。

**什么是 URLConnection 类？**
URLConnection 是一个抽象类，它的子类构成了用户应用程序和网络上任何资源之间的链接。我们可以使用它来读取/写入由 URL 对象引用的任何资源。

主要有两个子类扩展了 URLConnection 类-

*   **HttpurlConnection:** 如果我们连接到任何使用“http”作为协议的 URL，那么使用 HttpURLConnection 类。
*   **JarURLConnection:** If however, we are trying to establish a connection to a jar file on the web, then JarURLConnection is used.

    一旦建立了连接，并且我们有了一个 URLConnection 对象，我们就可以使用它来读取或写入或获取有关页面/文件上次修改时间、内容长度等的进一步信息。
    **重要方法**

    *   **URL connection openConnection():**打开到指定 URL 的连接。
    *   **对象 getContent():** 检索 URLConnection 的内容。
    *   **映射<字符串，列表> getHeaderFields():** 返回包含 http 头中各种头字段值的映射。
    *   **getContentEncoding():** 返回内容编码头字段的值。
    *   **getContentLength():** 返回内容头字段的长度。
    *   **getDate():** 返回表头字段的日期值。
    *   **getHeaderField(int i):** 返回表头第 i <sup>个</sup>索引的值。
    *   **getHeaderField(字符串字段):**返回标题
        中名为“Field”的字段的值要获得所有标题字段的列表，[读取此](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields)。
    *   **output stream getoutput stream():**将输出流返回到此连接。
    *   **InputStream getInputStream():**将输入流返回到这个打开的连接。
    *   **setallowserinteraction(布尔值):**设置为 true 意味着用户可以与页面交互。默认值为真。
    *   **设置默认用户缓存(布尔值):**将用户缓存字段的默认值设置为给定值。
    *   **setDoInput(布尔值):**设置是否允许用户输入。
    *   **setDoOutput(布尔值):**设置是否允许用户在页面上书写。默认值为 false，因为大多数 url 不允许写入。

    让我们看一个示例程序，它使用上述方法来显示标题字段，并将整个页面的源代码打印到控制台窗口上。

    ```
    //Java Program  to illustrate reading and writing
    // in URLConnection Class
    import java.io.*;
    import java.net.*;
    import java.util.ArrayList;
    import java.util.Date;
    import java.util.HashMap;
    import java.util.List;
    import java.util.Map;

    public class URLConnectionclass 
    {
        public static void main(String[] args) 
        {
            try
            {
                URL url = new URL("https://www.geeksforgeeks.org/java");

                //open the connection to the above URL.
                URLConnection urlcon = url.openConnection();

                //Executing the below line would print the value of
                // Allow User Interaction field.
                // System.out.println(urlcon.getAllowUserInteraction());

                //Executing the below line would print 
                // the value of Content Type field.
                // System.out.println(urlcon.getContentType());

                //Executing the below line would print the value 
                // of URL of the given connection.
                // System.out.println(urlcon.getURL());

                //Executing the below line would 
                // print the value of Do Input field.
                // System.out.println(urlcon.getDoInput());

                //Executing the below line would 
                // print the value of Do Output field.
                // System.out.println(urlcon.getDoOutput());

                //Executing the below line would 
                // print the value of Last Modified field.
                // System.out.println(new Date(urlcon.getLastModified()));

                //Executing the below line would 
                // print the value of Content Encoding field.
                // System.out.println(urlcon.getContentEncoding());

                //To get a map of all the fields of http header
                Map<String, List<String>> header = urlcon.getHeaderFields();

                //print all the fields along with their value.
                for (Map.Entry<String, List<String>> mp : header.entrySet()) 
                {
                    System.out.print(mp.getKey() + " : ");
                    System.out.println(mp.getValue().toString());
                }
                System.out.println();
                System.out.println("Complete source code of the URL is-");
                System.out.println("---------------------------------");

                //get the inputstream of the open connection.
                BufferedReader br = new BufferedReader(new InputStreamReader
                                                    (urlcon.getInputStream()));
                String i;

                //print the source code line by line.
                while ((i = br.readLine()) != null) 
                {
                    System.out.println(i);
                }
            } 

            catch (Exception e) 
            {
                System.out.println(e);
            }
        }
    }
    ```

    输出:

    ```
    Keep-Alive   :   [timeout=5, max=100]
    null   :   [HTTP/1.1 200 OK]
    Server   :   [Apache/2.4.18 (Ubuntu)]
    Connection   :   [Keep-Alive]
    Last-Modified   :   [Wed, 16 Nov 2016 06:49:55 GMT]
    Date   :   [Wed, 16 Nov 2016 10:58:34 GMT]
    Accept-Ranges   :   [bytes]
    Cache-Control   :   [max-age=3]
    ETag   :   ["10866-541657b07e4d7"]
    Vary   :   [Accept-Encoding]
    Expires   :   [Wed, 16 Nov 2016 10:58:37 GMT]
    Content-Length   :   [67686]
    Content-Type   :   

    Complete source code of the URL is-
    --------------------------------------------------

    ...source code of the page...

    ```

    **上述过程涉及的步骤:**

    1.  **网址创建:**使用任何给定的构造函数创建一个网址对象
    2.  [本](https://www.geeksforgeeks.org/url-class-java-examples/)条
    3.  **创建对象:**调用 openConnection()调用，创建 URLConnection 的对象。
    4.  **显示内容:**或者使用上面创建的对象显示关于资源的信息，或者使用 bufferedReader 将文件的内容读/写至控制台，并使用 getInputStream()方法输入打开连接的流。
    5.  **关闭流:**完成后关闭输入流。

    参考-[https://docs . Oracle . com/javase/7/docs/API/Java/net/urlconnection . html](https://docs.oracle.com/javase/7/docs/api/java/net/URLConnection.html)

    本文由**里沙布·马赫塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。