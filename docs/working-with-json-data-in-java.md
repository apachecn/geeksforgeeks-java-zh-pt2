# 用 Java 处理 JSON 数据

> 原文:[https://www . geesforgeks . org/work-with-JSON-data-in-Java/](https://www.geeksforgeeks.org/working-with-json-data-in-java/)

[**【JSON】**](https://www.geeksforgeeks.org/parse-json-java/)代表 JavaScript Object notification，这是一个轻量级的基于文本的开放标准，设计用于人类可读的数据交换。一般来说，JSON 是从 JavaScript 扩展而来的。JSON 独立于语言，易于读写。JSON 的文件扩展名是**。json** 。

**示例–JSON 格式**

在下面给出的示例中，您将看到如何以 JSON 格式存储值。考虑学生信息，其中 Stu_id、Stu_Name、课程是您需要存储的实体，然后以 JSON 格式，您可以以键值对的形式存储这些值。让我们看看。

```
{
   "Student": [

      {
         "Stu_id"   :  "1001",
         "Stu_Name" :  "Ashish",
         "Course"   :  "Java",
      },

      {
         "Stu_id"   :  "1002",
         "Stu_Name" :  "Rana",
         "Course"   :  "Advance Java",
      }
   ]
}

```

它是一种方法，通过这种方法，我们可以访问 Java 编程语言中读取或写入 JSON 数据的手段。这里我们简单地使用 **json.simple** 库通过 Java 访问这个特性意味着我们可以使用这个 **json.simple** 库在 Java 编程语言中对 JSON Object 进行编码或解码。现在，Java 的 json.simple 包包含以下文件。因此，要访问，我们首先必须安装 json.simple 包。

对于**安装**首先，我们需要在不同的情况下设置 json-simple.jar 类路径或者添加 Maven 依赖项。

**第一步:**使用此链接下载**JSON . simple**:[JSON . sample](https://www.dropbox.com/sh/wz8kpntgftjpbn9/AADU20oyJyAaYEHFUjRSvNEda?dl=0)
的下载链接

**步骤 2:** 还有一个方法可以添加 Maven 依赖项，为此，我们必须将下面给出的代码添加到我们的 *pom.xml* 文件中。

```
 <dependency>
    <groupId>com.googlecode.json-simple</groupId>  
    <artifactId>json-simple</artifactId>  
    <version>1.1</version>  
 </dependency>

```

以上下载的**。jar** 文件中包含这些 Java 源文件:

```
// .jar file 
META-INF/MANIFEST.MF
org.json.simple.ItemList.class
org.json.simple.JSONArray.class
org.json.simple.JSONAware.class
org.json.simple.JSONObject.class
org.json.simple.JSONStreamAware.class
org.json.simple.JSONValue.class
org.json.simple.parser.ContainerFactory.class
org.json.simple.parser.ContentHandler.class
org.json.simple.parser.JSONParser.class
org.json.simple.parser.ParseException.class
org.json.simple.parser.Yylex.class
org.json.simple.parser.Yytoken.class

```

### Java 中的 JSON 对象编码:

如上所述，这个 **json.simple** 库用于在 Java 中读取/写入或编码/解码 json 对象。让我们看看如何使用 ***JSONObject*** **函数**对 JSON 对象的一部分进行编码。现在我们创建一个 java 文件**mainEncoding.java**，并将下面写的代码保存在其中。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import org.json.simple.JSONObject;

// Program for print data in JSON format.
public class JavaJsonEncoding 
{
   public static void main(String args[])
   {
       // In java JSONObject is used to create JSON object  
       // which is a subclass of java.util.HashMap. 

       JSONObject file = new JSONObject();
       file.put("Full Name", "Ritu Sharma");
       file.put("Roll No.", new Integer(1704310046));
       file.put("Tution Fees", new Double(65400));

       // To print in JSON format.
       System.out.print(file);

   }
}
```

**输出:**

```
{"Full Name":"Ritu Sharma", "Roll No.":1704310046, "Tution Fees":65400}

```

现在我们来看看如何使用 ***JSONObject*** **函数**对 JSON 对象的一部分进行解码编码。现在我们创建一个 java 文件**mainDecoding.java**，并将下面写的代码保存在其中。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import org.json.simple.JSONObject;
import org.json.simple.JSONValue;

public class JavaJsonDecoding {

   public static void main(String[] args)
   {
       // Converting JSON data into Java String format
       String k = "{\"Full Name\":\"Ritu Sharma\",  
       \"Tution Fees\":65400.0, \"Roll No.\":1704310046}";
       Object file = JSONValue.parse(k);

       // In java JSONObject is used to create JSON object  
       JSONObject jsonObjectdecode = (JSONObject)file;

       // Converting into Java Data type
       // format From Json is the step of Decoding.
       String name = (String)jsonObjectdecode.get("Full Name");
       double fees = (Double)jsonObjectdecode.get("Tution Fees");
       long rollno = (Long)jsonObjectdecode.get("Roll No.");
       System.out.println(name + " " + fees + " " + rollno);
   }
}
```

**输出:**

```
Ritu Sharma 65400.0 1704310046

```

**注意:**这里 [Java JSON](https://www.geeksforgeeks.org/parse-json-java/#:~:text=JSON%20(JavaScript%20Object%20Notation)%20is,or%20more%20name%2Fvalue%20pairs.) 编码也可以使用[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)或者[地图](https://www.geeksforgeeks.org/map-interface-java-examples/)来完成。