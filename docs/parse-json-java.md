# 如何解析 Java 中的 JSON

> 哎哎哎:# t0]https://www . geeksforgeeks . org/parse-JSON-Java/

[JSON](http://json.org/)(JavaScript Object notification)是一种轻量级的、基于文本的、独立于语言的数据交换格式，便于人类和机器进行读写。JSON 可以表示两种结构化类型:对象和数组。对象是零个或多个名称/值对的无序集合。数组是由零个或多个值组成的有序序列。这些值可以是字符串、数字、布尔值、null 和这两种结构化类型。

下面是一个来自维基百科的简单例子，显示了描述一个人的对象的 JSON 表示。该对象具有名和姓的字符串值、年龄的数字值、代表个人地址的对象值以及电话号码对象的数组值。

```java
{
    "firstName": "John",
    "lastName": "Smith",
    "age": 25,
    "address": {
        "streetAddress": "21 2nd Street",
        "city": "New York",
        "state": "NY",
        "postalCode": 10021
    },
    "phoneNumbers": [
        {
            "type": "home",
            "number": "212 555-1234"
        },
        {
            "type": "fax",
            "number": "646 555-4567" 
        }
    ] 
}

```

**Java 中的 JSON 处理:**用于 JSON 处理的 Java API[JSON . simple](https://code.google.com/archive/p/json-simple/)是一个简单的 Java 库，允许解析、生成、转换和查询 JSON。

**入门:**在编译和运行下面的示例代码之前，您需要下载 [json-simple-1.1 jar](http://www.java2s.com/Code/Jar/j/Downloadjsonsimple11jar.htm) 并将其放入您的 CLASSPATH 中。

*   像 eclipse 一样在 IDE 中导入 jar，这里参考。
*   如果你正在使用 maven，你可以使用下面的 maven 链接[https://mvnrepository . com/artifact/com . googlecode . JSON-simple/JSON-simple/1 . 1 . 1](https://mvnrepository.com/artifact/com.googlecode.json-simple/json-simple/1.1.1)

**Json-Simple API :** 为 Json 对象和数组结构提供对象模型。这些 JSON 结构使用类型 **JSONObject** 和 **JSONArray** 表示为对象模型。JSONObject 提供了一个[映射](https://www.geeksforgeeks.org/map-interface-java-examples/)视图来访问模型中零个或多个名称/值对的无序集合。类似地，JSONArray 提供了一个[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)视图来访问模型中零个或多个值的有序序列。

**将 JSON 写入文件**

让我们看一个例子，在 JSONObject 和 JSONArray 的帮助下，将上面的 JSON 数据写入一个文件“JSONExample.json”。

```java
// Java program for write JSON to a file

import java.io.FileNotFoundException;
import java.io.PrintWriter;
import java.util.LinkedHashMap;
import java.util.Map;
import org.json.simple.JSONArray;
import org.json.simple.JSONObject;

public class JSONWriteExample
{
    public static void main(String[] args) throws FileNotFoundException 
    {
        // creating JSONObject
        JSONObject jo = new JSONObject();

        // putting data to JSONObject
        jo.put("firstName", "John");
        jo.put("lastName", "Smith");
        jo.put("age", 25);

        // for address data, first create LinkedHashMap
        Map m = new LinkedHashMap(4);
        m.put("streetAddress", "21 2nd Street");
        m.put("city", "New York");
        m.put("state", "NY");
        m.put("postalCode", 10021);

        // putting address to JSONObject
        jo.put("address", m);

        // for phone numbers, first create JSONArray 
        JSONArray ja = new JSONArray();

        m = new LinkedHashMap(2);
        m.put("type", "home");
        m.put("number", "212 555-1234");

        // adding map to list
        ja.add(m);

        m = new LinkedHashMap(2);
        m.put("type", "fax");
        m.put("number", "212 555-1234");

        // adding map to list
        ja.add(m);

        // putting phoneNumbers to JSONObject
        jo.put("phoneNumbers", ja);

        // writing JSON to file:"JSONExample.json" in cwd
        PrintWriter pw = new PrintWriter("JSONExample.json");
        pw.write(jo.toJSONString());

        pw.flush();
        pw.close();
    }
}
```

文件“JSONExample.json”的输出:

```java
{
     "lastName":"Smith",
    "address":{
        "streetAddress":"21 2nd Street",
         "city":"New York",
         "state":"NY",
         "postalCode":10021
    },
     "age":25,
     "phoneNumbers":[
            {
            "type":"home", "number":"212 555-1234"
            },
         {
            "type":"fax", "number":"212 555-1234"
         }
     ],
     "firstName":"John"
}

```

**注意:**在 JSON 中，对象是一组无序的名称/值对，因此 JSONObject 不会保留对象的名称/值对的顺序，因为它(根据定义)并不重要。因此在我们的输出文件中，顺序没有被保留。

**从文件中读取 JSON】**

让我们看一个例子，在 JSONParser、JSONObject 和 JSONArray 的帮助下，从上面创建的文件“JSONExample.json”中读取 JSON 数据。

```java
// Java program to read JSON from a file

import java.io.FileReader;
import java.util.Iterator;
import java.util.Map;

import org.json.simple.JSONArray;
import org.json.simple.JSONObject;
import org.json.simple.parser.*;

public class JSONReadExample 
{
    public static void main(String[] args) throws Exception 
    {
        // parsing file "JSONExample.json"
        Object obj = new JSONParser().parse(new FileReader("JSONExample.json"));

        // typecasting obj to JSONObject
        JSONObject jo = (JSONObject) obj;

        // getting firstName and lastName
        String firstName = (String) jo.get("firstName");
        String lastName = (String) jo.get("lastName");

        System.out.println(firstName);
        System.out.println(lastName);

        // getting age
        long age = (long) jo.get("age");
        System.out.println(age);

        // getting address
        Map address = ((Map)jo.get("address"));

        // iterating address Map
        Iterator<Map.Entry> itr1 = address.entrySet().iterator();
        while (itr1.hasNext()) {
            Map.Entry pair = itr1.next();
            System.out.println(pair.getKey() + " : " + pair.getValue());
        }

        // getting phoneNumbers
        JSONArray ja = (JSONArray) jo.get("phoneNumbers");

        // iterating phoneNumbers
        Iterator itr2 = ja.iterator();

        while (itr2.hasNext()) 
        {
            itr1 = ((Map) itr2.next()).entrySet().iterator();
            while (itr1.hasNext()) {
                Map.Entry pair = itr1.next();
                System.out.println(pair.getKey() + " : " + pair.getValue());
            }
        }
    }
}
```

输出:

```java
John
Smith
25
streetAddress : 21 2nd Street
postalCode : 10021
state : NY
city : New York
number : 212 555-1234
type : home
number : 212 555-1234
type : fax

```

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](https://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。