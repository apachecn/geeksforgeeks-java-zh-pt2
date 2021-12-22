# Java StAX 中的 XML stream writer

> 原文:[https://www.geeksforgeeks.org/xmlstreamwriter-in-java-stax/](https://www.geeksforgeeks.org/xmlstreamwriter-in-java-stax/)

Java 6 中添加的 XML 流应用编程接口提供了一个方便的接口 XMLStreamWriter，用于编写 XML 文档。这个 API 不需要像在 DOM 中那样构建任何特定的对象结构，也不需要做任何中间任务。默认情况下，它还支持名称空间，这在更高级的情况下非常有用。

为了创建 XMLStreamWriter 对象并将数据写入其中而合并的方法如下所示:

*   writeStartDocument()
*   writestartelemont_)
*   writeCharacters()
*   writeendelemont _)
*   writeEndDocument()

java StAX 中的 XMLStreamWriter 有一些限制，主要如下:

1.  You can still create malformed XML documents, such as documents with multiple root elements or missing namespace definitions.
2.  XMLStreamWriter does not indent its output, so it may be a bit difficult to read with a plain text editor. Therefore, for reading, it is recommended to open it in a web browser. Most browsers have a user-friendly interface to view the structure of XML documents.

**程序:**

1.  使用 XMLOutputFactory 创建 XMLStreamWriter 的实例
2.  编写 XML 的标题，然后继续编写元素。
3.  添加元素后，我们可以添加属性、字符数据或 CDATA
4.  关闭打开的元素
5.  清空元素或写评论
6.  关闭并完成 XML 文档

现在让我们进一步讨论它们是如何在 java 程序中实现的。

**步骤 1:** 使用 XMLOutputFactory 创建 XMLStreamWriter 的实例。

```
XMLOutputFactory outputFactory = XMLOutputFactory.newFactory();
XMLStreamWriter xmlStreamWriter = outputFactory.createXMLStreamWriter(outputStream);
```

**步骤 2:** 写下 XML 的头，然后继续写元素。

```
xmlStreamWriter.writeStartElement("gfg");
```

**第三步:**添加元素后，我们可以添加属性、字符数据或 CDATA。

```
xmlStreamWriter.writeAttribute("id", "10");
xmlStreamWriter.writeCharacters("hello world!");
xmlStreamWriter.writeCData("more text data");
```

**步骤 4:** 关闭打开的元素

```
xmlStreamWriter.writeEndElement();
```

**第 5 步:**清空元素或写评论，但一定要注意这是一个可选步骤

```
xmlStreamWriter.writeEmptyElement("used & new");
xmlStreamWriter.writeComment("Thank you!");
```

**步骤 6:** 关闭并完成 XML 文档。

```
xmlStreamWriter.writeEndDocument();
xmlStreamWriter.close();
```

**例**

## 爪哇

```
// Java Program to Illustrate XMLStreamWriter in Java StAX

// Importing required classes
import java.io.FileNotFoundException;
import java.io.FileWriter;
import java.io.UnsupportedEncodingException;
import java.io.Writer;
import javax.xml.stream.XMLOutputFactory;
import javax.xml.stream.XMLStreamException;
import javax.xml.stream.XMLStreamWriter;

// Main class
public class StaxXMLStreamWriter {

    // Main driver method
    public static void main(String[] args)
        throws FileNotFoundException, XMLStreamException,
               UnsupportedEncodingException
    {

        // Try block to check for exceptions
        try {

            // File Path
            String filePath = "D:\\gfg_file.xml";

            // Creating FileWriter object
            Writer fileWriter = new FileWriter(filePath);

            // Getting the XMLOutputFactory instance
            XMLOutputFactory xmlOutputFactory
                = XMLOutputFactory.newInstance();

            // Creating XMLStreamWriter object from
            // xmlOutputFactory.
            XMLStreamWriter xmlStreamWriter
                = xmlOutputFactory.createXMLStreamWriter(
                    fileWriter);

            // Addoing elements to xmlStreamWriter
            // Custom input element addition
            xmlStreamWriter.writeStartElement("gfg");
            xmlStreamWriter.writeAttribute("id", "10");
            xmlStreamWriter.writeCharacters("hello world!");
            xmlStreamWriter.writeCData("more text data");
            xmlStreamWriter.writeEndElement();
            xmlStreamWriter.writeEmptyElement("used & new");
            xmlStreamWriter.writeComment("Thank you!");
            xmlStreamWriter.writeEndDocument();

            // Writing the content on XML file and
            // close xmlStreamWriter using close() method
            xmlStreamWriter.flush();
            xmlStreamWriter.close();

            // Display message for successful execution of
            // program
            System.out.println(
                "XML file created successfully.");
        }

        // Catch block to handle exceptions
        catch (Exception e) {

            // Print the line number where exception occurs
            e.printStackTrace();
        }
    }
}
```

**输出:**

```
<gfg id="10">hello world!
<![CDATA[more text data]]>
</gfg>
<used & new/>
<!--Thank you!-->
```

**结论:**

XML 的流应用编程接口提供了一种非常方便、快速和节省内存的方式来编写 XML 文档，而不用担心细节和转义特殊字符。它是 DOM 的一个很好的替代品，尤其是当你不需要出于任何原因在内存中保存和管理 [DOM 树](https://www.geeksforgeeks.org/dom-document-object-model/)的时候。