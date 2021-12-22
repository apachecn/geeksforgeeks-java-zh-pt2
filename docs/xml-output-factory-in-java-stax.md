# Java statx 中的 XML 输出工厂

> 原文:[https://www . geesforgeks . org/XML-output-factory-in-Java-statx/](https://www.geeksforgeeks.org/xml-output-factory-in-java-stax/)

StAX 提供了各种类，通过使用 XMLInputFactory、XMLOutputFactory 和 XMLEventFactory 类来创建 XML 流读取器、写入器和事件。在本文中，我们将研究 **XML 输出工厂**。类 javax . XML . stream . xmloutputfactory 是 Java StAX API 的根组件。*从这个类中你可以创建一个*[*XMLStreamWriter*](https://www.geeksforgeeks.org/xmlstreamwriter-in-java-stax/)*和一个*[*XMLEventWriter*](https://www.geeksforgeeks.org/xml-eventwriter-in-java-stax-api/)*。*

> **注意:**XMLOutputFactory 只保留一个属性，javax . XML . stream . isreparing Namespace .这个属性是必需的，它的目的是创建默认前缀，并将其与 Namespace URIs 相关联。
> 
> T21】

### 程序:

1.  使用 newInstance()方法创建一个新的 XMLOutputFactory 抽象类。
2.  使用 XMLOutputFactory 实例创建 XMLStreamWriter 或 XMLEventWriter 的实例。
3.  编写 XML 的标题
4.  创建语句
5.  添加元素，这样我们就可以添加属性、名称空间。
6.  冲洗并关闭打开的元件
7.  添加尝试和捕捉块

**如下图所示:**

**步骤 1:** 通过调用 new instance()方法

```java
XMLOutputFactory factory = XMLOutputFactory.newInstance();
```

创建抽象类 XMLOutputFactory 的新实例

**步骤 2:** 使用这个实例，创建一个 XMLStreamWriter 和一个 XMLEventWriter

```java
XMLEventWriter eventWriter = factory.createXMLEventWriter(new FileWriter("data\\gfg.xml"));
XMLStreamWriter streamWriter = factory.createXMLStreamWriter(new FileWriter("data\\gfg.xml"));
```

**第 3 步:**编写 XML 的头部，并继续创建开始元素。

```java
XMLEvent event = eventFactory.createStartDocument();
event = eventFactory.createStartElement("GFG", "https://www.geeksforgeeks.org/", "document");
```

**第四步:**添加元素后我们可以添加属性，命名空间。

```java
event = eventFactory.createNamespace("GeeksforGeeks-practice", "https://practice.geeksforgeeks.org/");
writer.add(event);
event = eventFactory.createAttribute("attribute", "value");
writer.add(event);
```

**步骤 5:** 冲洗并关闭打开的元素。

```java
writer.flush();
writer.close();
```

**第六步:**添加试捕块。

```java
try 
    {
       --code--
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

### **XMLOutputFactory 示例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
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
        XMLOutputFactory factory= XMLOutputFactory.newInstance();

        // Getting the XMLEventFactory instance
        XMLEventFactory eventFactory = XMLEventFactory.newInstance();

        // Try block for error hadeling
        try {

            // Creating EventWriter object using factory(instance)
            XMLEventWriter writer = factory.createXMLEventWriter(new FileWriter("D:\\gfg_OutputFactory.xml"));

            // Creating XMLEvent object using  eventFactory(instance)
            XMLEvent event = eventFactory.createStartDocument();
            writer.add(event);

            // Creating a start element
            event = eventFactory.createStartElement("GFG", "https://www.geeksforgeeks.org/","document");
            writer.add(event);

            // Creating namespace
            event = eventFactory.createNamespace("GeeksforGeeks-practice","https://practice.geeksforgeeks.org/");
            writer.add(event);

            // Setting attributes
            event = eventFactory.createAttribute("attribute", "GFG");
            writer.add(event);

            // Lastly creating end element
            event = eventFactory.createEndElement("GFG", "http://gfg.com", "document");
            writer.add(event);

            // Flush and close xmlEventWriter
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

### 输出:

```java
<?xml version='1.0' encoding='UTF-8'?>
<GFG:document xmlns:GeeksforGeeks-practice="https://practice.geeksforgeeks.org/" attribute="GFG>
</GFG:document>
```