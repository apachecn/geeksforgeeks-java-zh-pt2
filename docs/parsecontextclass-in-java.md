# Java 中的 parsecontextclass 类

> 原文:[https://www.geeksforgeeks.org/parsecontextclass-in-java/](https://www.geeksforgeeks.org/parsecontextclass-in-java/)

**ParseContext** 类是 Java package org . Apache . Tika . parser 的一个组件，用于解析上下文并将其传递给**Tika**(Apache Tika 工具包从一千多个不同的文件类型中检测并提取元数据和文本)解析器**org . Apache . Tika . parser . parse context**实现了一个 Serializable 接口。

```java
public class ParseContext extends Object implements Serializable
```

### **施工方:**

**1。ParseContext()–**parse context()初始化 parse context 类的一个新实例。

```java
ParseContext p = new ParseContext()
```

> **注意:** p 是 ParseContext 类的新实例。

### ParseContext 的方法–

<figure class="table">

| 

没有。

 | 

方法

 | 

描述

 | 返回类型 |
| --- | --- | --- | --- |
| 

1.

 | **getDocumentBuilder()** | getDocumentBuilder()返回在这个解析上下文中指定的 DOM 构建器。 | DocumentBuilder |
| 

2.

 | **山羊剪刀分析器()** | getSAXParser()返回在这个解析上下文中指定的 SAX 解析器。 | 萨克斯风手吗 |
| 

3.

 | **getsaxerserfactory()** | getSAXParserFactory()返回在这个解析上下文中指定的 SAX 解析器工厂。 | SAXParserFactory |
| 

4.

 | **getter()** | getTransformer()返回在此解析上下文中指定的转换器。 | 变压器 |
| 

5.

 | **getxmlnputfactory()** | getXMLInputFactory()返回在此解析上下文中指定的 StAX 输入工厂。 | XMLInputFactory |
| 

6.

 | **getXMLReader()** | getXMLReader()返回在此解析上下文中指定的 XMLReader。 | XMLReader |
| 

7.

 | **获取(类< T >键)** | get(Class <t>键)返回这个上下文中实现给定接口的对象。</t> | <t>T</t> |
| 

8.

 | **获取(类< T >键，T 默认值)** | get(Class <t>键，T defaultValue)返回这个上下文中实现给定接口的对象。</t> | <t>T</t> |
| 

9.

 | **设置(类< T >键，T 值)** | set(Class <t>键，T 值)将给定值添加到上下文中，实现给定的接口。</t> | <t>无效</t> |

</figure>

### 示例:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program To Get Content of the
// document using Tika Toolkit and 
// ContextParser:
import java.io.*;

// importing File class
import java.io.File.*;
import org.apache.tika.exception.TikaException;
import org.apache.tika.metadata.Metadata;
import org.apache.tika.parser.ParseContext;
import org.apache.tika.parser.txt.TXTParser;
import org.apache.tika.sax.BodyContentHandler;
// import the necessary Tika packages
import org.xml.sax.SAXException;

class GFG {
    public static void main(String[] args)
    {
        // new instance of FIle is created
        File fileName = new File("tmp.txt");

        // new instance of FileInputStream is created for
        // reading purpose
        FileInputStream fileInputStream
            = new FileInputStream(fileName);

        // new instance of parseContext class is created
        ParseContext parseContext = new ParseContext();

        // new instance of MetaData is created
        MetaData metaData = new MetaData();

        // new instance of TXTParser is created for plain
        // text parsing purpose
        TXTParser textParser = new TXTParser();

        // new instance of BodyContentHandler is created
        BodyContentHandler bodyContentHandler
            = new BodyContentHandler();

        // TXTParser parse method is called for parsing a
        // document stream into sequence of XHTML SAX events.
        textParser.parse(fileInputStream,
                         bodyContentHandler, metaData,
                         parseContext);

        System.out.println("Contents of the document:"
                           + bodyContenthandler.toString());
    }
}
```

**输出-**

```java
Contents of the document:GFG is the best website for programmer
```

**注意–****tmp . txt**文件包含以下数据。

![](img/a3dc058f1a37b19fea8d2f5d39b50e22.png)