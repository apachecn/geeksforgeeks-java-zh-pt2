# 使用 Java 程序发送邮件

> 原文:[https://www . geesforgeks . org/send-email-use-Java-program/](https://www.geeksforgeeks.org/send-email-using-java-program/)

发送电子邮件是一个基本要求，无论你在哪个平台上工作，如 JAVA、JavaEE、Python 等。发送电子邮件可能需要发送错误警报或注册或注册确认。java 通过编写 Java 程序来提供发送电子邮件的功能。
使用 Java 发送邮件，需要三样东西:

*   JavaMail API
*   Java 激活框架(JAF)
*   您的 SMTP 服务器详细信息

您可以从 Java 的官方网站下载最新版本的 JavaMail 应用编程接口和 JAF。成功下载这两个后，提取它们。在类路径中添加 **mail.jar** 、 **smtp.jar** 和 **activation.jar** 文件，以便有资格发送电子邮件。
添加完这些文件后，按照下面的步骤，编写一个 java 程序发送邮件:

*   通过调用 getDefaultInstance()方法创建一个新的会话对象，并将属性作为参数传递，以获取所有重要的属性，如 SMTP 服务器的主机名等。
*   通过传递上一步中创建的会话对象来创建 MimeMessage 对象。

*   最后一步是使用 javax.mail.Transport 发送电子邮件

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to send email

import java.util.*;
import javax.mail.*;
import javax.mail.internet.*;
import javax.activation.*;
import javax.mail.Session;
import javax.mail.Transport;

public class SendEmail
{

   public static void main(String [] args)
   {   
      // email ID of Recipient.
      String recipient = "recipient@gmail.com";

      // email ID of  Sender.
      String sender = "sender@gmail.com";

      // using host as localhost
      String host = "127.0.0.1";

      // Getting system properties
      Properties properties = System.getProperties();

      // Setting up mail server
      properties.setProperty("mail.smtp.host", host);

      // creating session object to get properties
      Session session = Session.getDefaultInstance(properties);

      try
      {
         // MimeMessage object.
         MimeMessage message = new MimeMessage(session);

         // Set From Field: adding senders email to from field.
         message.setFrom(new InternetAddress(sender));

         // Set To Field: adding recipient's email to from field.
         message.addRecipient(Message.RecipientType.TO, new InternetAddress(recipient));

         // Set Subject: subject of the email
         message.setSubject("This is Subject");

         // set body of the email.
         message.setText("This is a test mail");

         // Send email.
         Transport.send(message);
         System.out.println("Mail successfully sent");
      }
      catch (MessagingException mex)
      {
         mex.printStackTrace();
      }
   }
}
```

输出:

```java
Mail successfully sent
```

**向多个收件人发送电子邮件**

向多个收件人发送电子邮件与向单个收件人发送电子邮件相同。不同的是，要向多个收件人发送邮件，您应该添加多个收件人。要添加多个收件人，我们必须调用以下方法，并将收件人类型和电子邮件地址列表作为参数传递:

```java
void addRecipients(Message.RecipientType type, Address[] addresses) 
   throws MessagingException
   {

   }
```

要在“收件人”字段中添加电子邮件，您可以使用“邮件”。收件人类型。收件人。同样，要在“抄送”和“密件抄送”字段中添加电子邮件，您必须使用“邮件”。收件人类型。抄送和邮件。收件人类型。密件抄送
上述方法中的参数**地址**是一个包含所有电子邮件标识列表的数组。您必须使用互联网地址()方法来指定电子邮件。
假设你想给 4 个人发邮件。您必须创建一个大小为 4 的字符串数组，并将收件人的电子邮件地址存储在其中。按照上面的程序发送一封简单的电子邮件，而不是添加一个收件人，使用如下所示的添加收件人方法添加多个收件人:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// create a new String array
String[] recipients = new String[4];

// add email addresses
recipients[0] = first@gmail.com
recipients[1] = second@gmail.com
recipients[2] = third@gmail.com
recipients[3] = fourth@gmail.com

// inside of try block instead of using addRecipient()
// use addRecipients()

// specify the type of field(TO, CC ,BCC)
// pass the array of email ids of recipients
message.addRecipient(Message.RecipientType.TO, new InternetAddress(recipients));
```

**用 HTML 模板发送邮件**

有些时候，电子邮件是用超文本标记语言模板发送的，即电子邮件的正文是用超文本标记语言编写的。这使得电子邮件格式良好，外观吸引人。用 HTML 模板发送邮件的程序和发送普通邮件的程序几乎一样。不同的是，我们必须使用 *setContent()* 方法而不是 *setText()* 方法来指定电子邮件的正文，在方法 **setContent()** 中，我们必须将第二个参数指定为“text/html”，第一个参数将是 html 代码。现在让我们看看用 HTML 模板发送电子邮件的程序:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to send email
// with HTML templates

import java.util.*;
import javax.mail.*;
import javax.mail.internet.*;
import javax.activation.*;
import javax.mail.Session;
import javax.mail.Transport;

public class SendEmail
{

   public static void main(String [] args)
   {   
      // email ID of Recipient.
      String recipient = "recipient@gmail.com";

      // email ID of  Sender.
      String sender = "sender@gmail.com";

      // using host as localhost
      String host = "127.0.0.1";

      // Getting system properties
      Properties properties = System.getProperties();

      // Setting up mail server
      properties.setProperty("mail.smtp.host", host);

      // creating session object to get properties
      Session session = Session.getDefaultInstance(properties);

      try
      {
         // MimeMessage object.
         MimeMessage message = new MimeMessage(session);

         // Set From Field: adding senders email to from field.
         message.setFrom(new InternetAddress(sender));

         // Set To Field: adding recipient's email to from field.
         message.addRecipient(Message.RecipientType.TO, new InternetAddress(recipient));

         // Set Subject: subject of the email
         message.setSubject("This is Subject");

         // set body of the email.
         message.setContent("<h1>This is a HTML text</h1>","text/html");

         // Send email.
         Transport.send(message);
         System.out.println("Mail successfully sent");
      }
      catch (MessagingException mex)
      {
         mex.printStackTrace();
      }
   }
}
```

输出:

```java
Mail successfully sent
```

**发送带有附件的电子邮件**

JavaMail 应用编程接口允许您发送包含附件的电子邮件。要发送带有附件的电子邮件，我们必须创建两个 MimeBodyPart 对象，并将文本分配给一个对象，并将数据处理程序分配给另一个对象。发送带有附件的电子邮件的过程简述如下:

*   创建新的会话对象
*   创建一个 MimeBodyPart 对象并为其分配文本
*   创建一个新的 MimeBodyPart 对象，并为其分配数据处理程序对象
*   创建一个多部分对象，并将两个模拟身体部分对象分配给这个多部分对象
*   将此多部分对象设置为消息。SetContent()方法。
*   使用 Transport()方法发送邮件

现在让我们来看看做这个的程序:

## 卡片打印处理机（Card Print Processor 的缩写）

```java
// Java program to send email
// with attachments

import java.util.*;
import javax.mail.*;
import javax.mail.internet.*;
import javax.activation.*;
import javax.mail.Session;
import javax.mail.Transport;

public class SendEmail
{

    public static void main(String [] args)
    {
        // email ID of Recipient.
        String recipient = "recipient@gmail.com";

        // email ID of Sender.
        String sender = "sender@gmail.com";

        // using host as localhost
        String host = "127.0.0.1";

        // Getting system properties
        Properties properties = System.getProperties();

        // Setting up mail server
        properties.setProperty("mail.smtp.host", host);

        // creating session object to get properties
        Session session = Session.getDefaultInstance(properties);

        try
        {
            // MimeMessage object.
            MimeMessage message = new MimeMessage(session);

            // Set From Field: adding senders email to from field.
            message.setFrom(new InternetAddress(sender));

            // Set To Field: adding recipient's email to from field.
            message.addRecipient(Message.RecipientType.TO, new InternetAddress(recipient));

            // Set Subject: subject of the email
            message.setSubject("This is Subject");

            // creating first MimeBodyPart object
            BodyPart messageBodyPart1 = new MimeBodyPart();
            messageBodyPart1.setText("This is body of the mail");

            // creating second MimeBodyPart object
            BodyPart messageBodyPart2 = new MimeBodyPart();
            String filename = "attachment.txt"
            DataSource source = new FileDataSource(filename); 
            messageBodyPart2.setDataHandler(new DataHandler(source)); 
            messageBodyPart2.setFileName(filename); 

            // creating MultiPart object
            Multipart multipartObject = new MimeMultipart(); 
            multipartObject.addBodyPart(messageBodyPart1); 
            multipartObject.addBodyPart(messageBodyPart2);

            // set body of the email.
            message.setContent(multipartObject);

            // Send email.
            Transport.send(message);
            System.out.println("Mail successfully sent");
        }
        catch (MessagingException mex)
        {
            mex.printStackTrace();
        }
    }
}
```

输出:

```java
Mail successfully sent
```

**注意**:这里我们使用了 localhost SMTP 服务器发送邮件。如果你想使用任何电子邮件发送客户端，如 Gmail，雅虎等，那么你将不得不使用各自的 SMTP 服务器主机地址。
本文由 [**严酷的阿加瓦尔**](https://www.facebook.com/harsh.agarwal.16752) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。