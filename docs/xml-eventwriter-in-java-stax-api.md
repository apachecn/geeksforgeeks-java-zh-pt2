# Java statx API 中的 XML event writer

> 原文:[https://www . geesforgeks . org/XML-event writer-in-Java-StAX-API/](https://www.geeksforgeeks.org/xml-eventwriter-in-java-stax-api/)

[Java StAX API](https://www.geeksforgeeks.org/xmlstreamwriter-in-java-stax/) 是在 Java 6 中引入的，被认为优于 DOM 和 SAX 解析器。我们可以使用 Java StAX 解析器读取 XML 文件，Java Streaming API for XML(Java StAX)提供了用 Java 处理 XML 的实现。Java StAX 应用编程接口中的 **XMLEventWriter** 类允许您将 StAX XMLEvent 写入一个 Writer、一个 OutputStream 或一个 Result(特殊的 JAXP 对象)。

XMLEventWriter 提供的将数据写入其中的方法:

*   创建 startdocument()
*   创建 startellemon_)
*   创建属性()
*   创建命名空间()
*   createEndElement()

java StAX 中的 XMLEventWriter 有一些限制，主要如下:

1.  XMLEventWriter does not indent its output, so it may be a bit difficult to read with a plain text editor. Therefore, for reading, it is recommended to open it in a web browser. Most browsers have a user-friendly interface to view the structure of XML documents.
2.  It is still possible to create malformed XML documents, such as documents with multiple root elements or missing namespace definitions.

**程序:**

*   创建 XMLEventWriter 的实例
*   编写 XML 的标题
*   创建语句
*   添加元素，这样我们就可以添加属性、名称空间。
*   冲洗并关闭打开的元件
*   添加尝试和捕捉块

它们如下所示:

**步骤 1 :** 使用 XMLOutputFactory 创建 XMLEventWriter 的实例。

```java
XMLOutputFactory factory = XMLOutputFactory.newInstance();
XMLEventFactory eventFactory = XMLEventFactory.newInstance();
XMLEventWriter writer =factory.createXMLEventWriter(
new FileWriter("F:\\gfg-XmlFile.xml"));
```

**第 2 步:**编写 XML 的头部，并继续创建开始元素。

```java
XMLEvent event = eventFactory.createStartDocument();
event = eventFactory.createStartElement("GFG", "https://www.geeksforgeeks.org/", "document");
```

**第三步:**添加元素后我们可以添加属性，命名空间。

```java
event = eventFactory.createNamespace("GeeksforGeeks-practice",
"https://practice.geeksforgeeks.org/");

writer.add(event);
event = eventFactory.createAttribute("attribute", "value");
writer.add(event);
```

**步骤 4:** 冲洗并关闭打开的元素。

```java
writer.flush();
writer.close();
```

**第五步:**添加试捕块。

```java
try 
    {
  ----------code------------
    } 
catch (XMLStreamException e) 
    {
     e.printStackTrace();
    } 
catch (IOException e) 
    {
    e.printStackTrace();
    }
```

**例**

## 爪哇

```java
// Java Program to Illustrate XML EventWriter in StAX API

// Importing required classes
import java.io.*;
import javax.xml.stream.XMLEventFactory;
import javax.xml.stream.XMLEventWriter;
import javax.xml.stream.XMLOutputFactory;
import javax.xml.stream.XMLStreamException;
import javax.xml.stream.events.XMLEvent;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Getting the XMLOutputFactory instance
        XMLOutputFactory factory
            = XMLOutputFactory.newInstance();

        // Getting the XMLEventFactory instance
        XMLEventFactory eventFactory
            = XMLEventFactory.newInstance();

        // Try block to check for exceptions
        try {

            // Creating EventWriter object
            XMLEventWriter writer
                = factory.createXMLEventWriter(
                    new FileWriter("F:\\gfg-XmlFile.xml"));
            XMLEvent event
                = eventFactory.createStartDocument();
            writer.add(event);

            // Creating a start element
            event = eventFactory.createStartElement(
                "GFG", "https://www.geeksforgeeks.org/",
                "document");
            writer.add(event);

            // Cteating namespace
            event = eventFactory.createNamespace(
                "GeeksforGeeks-practice",
                "https://practice.geeksforgeeks.org/");
            writer.add(event);

            // Setting attributes
            event = eventFactory.createAttribute(
                "attribute", "GFG");
            writer.add(event);

            // Lastly creating ana end element
            event = eventFactory.createEndElement(
                "GFG", "http://gfg.com", "document");
            writer.add(event);

            // Flush and close xmlEventWriter
            // using close() and flush() method
            // It is always a good practice
            writer.flush();
            writer.close();
        }

        // Catch block to handle exceptions
        catch (XMLStreamException e) {

            // Print line number where exception occurs
            // using printStacktrace() method
            e.printStackTrace();
        }
        catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

**输出:**

```java
<?xml version='1.0' encoding='UTF-8'?>
<GFG:document xmlns:GeeksforGeeks-practice="https://practice.geeksforgeeks.org/" attribute="GFG>
</GFG:document>
```

> **注:**针对 XML 的 Streaming Event Writer API 提供了一种非常方便、快速且节省内存的方式来编写 XML 文档，而无需担心细节和转义特殊字符。它是 DOM 的一个很好的替代品，尤其是当你不需要出于任何原因在内存中保存和管理 DOM 树的时候。