# Java 中的 UnrecognizedPropertyException 异常

> 原文:[https://www . geeksforgeeks . org/unrecorded property exception-in-Java/](https://www.geeksforgeeks.org/unrecognizedpropertyexception-in-java/)

在 Restful Web 服务应用程序中，我们解析一个 JSON 请求字符串，然后将其映射到一个 java 类。使用杰克逊库将 JSON 字符串解组到 java 类中。如果 JSON 字符串包含无法映射到 java 类属性的属性，那么我们会遇到[unrecognized property exception](https://www.geeksforgeeks.org/how-to-ignore-unknown-properties-while-parsing-json-in-java/)。让我们通过下面的插图来理解这一点。

> **说明:**
> 
> 我们有一个 Employee 类，有姓名、身份证、部门、工资等属性。然后我们用所有这些属性创建一个 json 字符串。然后，我们将尝试将 JSON 字符串反序列化为 Employee 类。

在 eclipse 中设置时，我们需要创建一个 maven 项目，并在*“POM . XML 文件”*中添加以下依赖项。

```java
    <dependencies>
        <dependency>

            <groupId>com.fasterxml.jackson.core</groupId>
            <artifactId>jackson-databind</artifactId>
            <version>2.2.3</version>
        </dependency>

    </dependencies>
```

这将在我们的项目中下载以下 jar。

```java
jackson-databind-2.2.3.jar
jackson-annotations-2.2.3.jar
jackson-core-2.2.3.jar
```

现在继续，让我们使用 Jackson 库进行序列化和反序列化，其中我们使用 Jackson 库将 employee 对象序列化为 json 文件，该文件是在 *src/main/resources 文件夹中创建的。Jackson 的库*也有 *API* s，它可以打印 json 文件，如下图所示。

**例**

## 爪哇

```java
// Java Program to Serialize and Deserialize
// Using the Jackson library

// Importing input output classes
// Importing Jackson classes
import com.fasterxml.jackson.core.JsonGenerationException;
import com.fasterxml.jackson.databind.JsonMappingException;
import com.fasterxml.jackson.databind.ObjectMapper;
import java.io.*;
import java.io.File;
import java.io.IOException;

// Helper class
class Employee {

    // Member variables of this class
    private String id;
    private String name;
    private String deptName;
    private double salary;

    // Member functions
    public String getId() { return id; }
    public void setId(String id) { this.id = id; }
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    public String getDeptName() { return deptName; }
    public void setDeptName(String deptName)
    {
        this.deptName = deptName;
    }
    public double getSalary() { return salary; }
    public void setSalary(double salary)
    {
        this.salary = salary;
    }
}

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // creates an object mapper instance
        ObjectMapper mapper = new ObjectMapper();

        // creates an employee instance.
        Employee employee = generateEmployee();

        // java object to json

        // Try block to check for exceptions
        try {

            // Serializes the java object to json and
            // creates a file in src/main/resources
            mapper.writeValue(
                new File(
                    "/home/suchitra/Desktop/suchitra/projects/java-concurrency-examples/json-parsing/src/main/resources/emp.json"),
                employee);

            // Creating a json string
            String empJson
                = mapper.writeValueAsString(employee);

            // Print and display
            System.out.println(empJson);

            // Pretty print
            String empJsonPrettyPrint
                = mapper.writerWithDefaultPrettyPrinter()
                      .writeValueAsString(employee);

            System.out.println("Pretty print format");
            System.out.println(empJsonPrettyPrint);
        }

        // Catch block 2
        // Catch block to handle exceptions
        // related to json generation
        catch (JsonGenerationException e) {

            // Print the exception along with line number
            // using printStackTrace() method
            e.printStackTrace();
        }

        // Catch block 2
        // Catch block to handle exceptions
        // related to json mapping
        catch (JsonMappingException e) {
            e.printStackTrace();
        }

        // Catch block 3
        // Catch block to handle basic exceptions
        catch (IOException e) {
            e.printStackTrace();
        }

        // Convert to a json string
    }

    private static Employee generateEmployee()
    {

        Employee employee = new Employee();
        employee.setId("e01010");
        employee.setName("Jane");
        employee.setDeptName("Sales");
        employee.setSalary(100000.00);

        return employee;
    }
}
```

**输出:**

```java
{"id":"e01010","name":"Jane","deptName":"Sales","salary":100000.0}
Pretty print format
{
  "id" : "e01010",
  "name" : "Jane",
  "deptName" : "Sales",
  "salary" : 100000.0
}
```

文件 emp.json 在 src/main/resources 文件夹中创建。

```java
{"id":"e01010","name":"Jane","deptName":"Sales","salary":100000.0}
```

现在让我们通过一个例子来理解 UnrecognizedPropertyException，当我们解析 json 文件时，什么时候会得到这个异常。

**实施:**

*   我们创建了一个 json 文件，其中添加了一个新属性 phoneNumber。但是，该属性不在 Employee 类中。
*   当 Jackson 库试图将 json 字段值解组/反序列化为类属性时，它无法识别该属性，并引发 UnrecognizedPropertyException。
*   我们在 src/main/resources 中创建了一个文件 emp1.json。文件 emp1.json 有一个不属于 Employee 类的新属性 phoneNumber。

```java
{"id":"e01010","name":"Jane","deptName":"Sales","salary":100000.0,"phoneNumber": 98218281812}
```

**例**

## 爪哇

```java
// Java Program to Illustrate UnrecognizedPropertyException
// While parsing json files

// Importing input output classes
import java.io.*;

// Class 1
// Helper class
class Employee {

    // Member variables of this class
    private String id;
    private String name;
    private String deptName;
    private double salary;

    // Member functions of this class

    public String getId() { return id; }

    public void setId(String id) { this.id = id; }

    public String getName() { return name; }

    public void setName(String name) { this.name = name; }

    public String getDeptName() { return deptName; }

    public void setDeptName(String deptName)
    {
        this.deptName = deptName;
    }

    public double getSalary() { return salary; }

    public void setSalary(double salary)
    {
        this.salary = salary;
    }

    @Override public String toString()
    {
        return "Employee [id=" + id + ", name=" + name
            + ", deptName=" + deptName
            + ", salary=" + salary + "]";
    }
}

// Class 2
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of ObjectMapper class
        ObjectMapper mapper = new ObjectMapper();

        // Try block to check for exceptions
        try {

            // mapper reads from json file and deserializes
            // it to Employee object
            Employee emp = mapper.readValue(
                new File(
                    "/home/suchitra/Desktop/suchitra/projects/java-concurrency-examples/json-parsing/src/main/resources/emp1.json"),
                Employee.class);
            System.out.println(
                "Reading values of employee attributes from a json file");
            System.out.println(emp.toString());
        }

        // Catch Block 1
        // Handling json parsing exception
        catch (JsonParseException e) {

            // Print and display the exception along with
            // line number using printStackTrace() method
            e.printStackTrace();
        }

        // Catch Block 2
        // Handling json mapping exception
        catch (JsonMappingException e) {
            e.printStackTrace();
        }

        // Catch Block 3
        // Catch block to handle basic exceptions
        catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

**输出:**

```java
com.fasterxml.jackson.databind.exc.UnrecognizedPropertyException: Unrecognized field "phoneNumber" (class com.sample.json.Employee), not marked as ignorable (4 known properties: , "deptName", "salary", "id", "name"])
 at [Source: /home/suchitra/Desktop/suchitra/projects/java-concurrency-examples/json-parsing/src/main/resources/emp1.json; line: 1, column: 93] (through reference chain: com.sample.json.Employee["phoneNumber"])
    at com.fasterxml.jackson.databind.exc.UnrecognizedPropertyException.from(UnrecognizedPropertyException.java:79)
    at com.fasterxml.jackson.databind.DeserializationContext.reportUnknownProperty(DeserializationContext.java:555)
    at com.fasterxml.jackson.databind.deser.std.StdDeserializer.handleUnknownProperty(StdDeserializer.java:708)
    at com.fasterxml.jackson.databind.deser.BeanDeserializerBase.handleUnknownProperty(BeanDeserializerBase.java:1160)
    at com.fasterxml.jackson.databind.deser.BeanDeserializer.deserializeFromObject(BeanDeserializer.java:315)
    at com.fasterxml.jackson.databind.deser.BeanDeserializer.deserialize(BeanDeserializer.java:121)
    at com.fasterxml.jackson.databind.ObjectMapper._readMapAndClose(ObjectMapper.java:2888)
    at com.fasterxml.jackson.databind.ObjectMapper.readValue(ObjectMapper.java:1988)
    at com.sample.json.TestParsingException.main(TestParsingException.java:19)
```

> **注意:**异常表示无法识别属于 emp1.json 文件一部分的属性 phoneNumber。这是因为它无法将此属性与 Employee 类的属性进行映射。

现在让我们讨论一个摆脱这种例外的方法。下面是我们可以合并的两种方法，如下所示:

1.  Disable object mapper to deserialize unknown attributes.
2.  Provide class-level comments @ JsonIgnoreProperties.

**方法 1:** 禁用对象映射器对未知属性进行反序列化。

为了解决这个问题，我们禁用对象映射器对未知属性进行反序列化。因此，对象映射器将只解组/反序列化 json 文件中映射到 java 类的那些属性。我们有 emp1.json，它类似于前面的例子。

```java
<u>emp1.json</u>
{"id":"e01010","name":"Jane","deptName":"Sales","salary":100000.0,"phoneNumber": 98218281812}
```

**例**

## 爪哇

```java
// Java Program to Remove UnrecognizedPropertyException by
// Disabling the object mapper to deserialize on unknown
// properties.

package com.sample.json;
// Importing input output classes
import java.io.*;

// Class 1
// Helper class
public class Employee {

    // Member variables of this class
    private String id;
    private String name;
    private String deptName;
    private double salary;

    // Member methods of this class
    public String getId() { return id; }
    public void setId(String id) { this.id = id; }
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    public String getDeptName() { return deptName; }
    public void setDeptName(String deptName)
    {
        this.deptName = deptName;
    }
    public double getSalary() { return salary; }
    public void setSalary(double salary)
    {
        this.salary = salary;
    }
    @Override public String toString()
    {
        return "Employee [id=" + id + ", name=" + name
            + ", deptName=" + deptName
            + ", salary=" + salary + "]";
    }
}

// Class 2
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of ObjectMapper class
        ObjectMapper mapper = new ObjectMapper();

        // Try block to check for exceptions
        try {

            // Disabling the mapper object to deserialize
            // properties which cannot be mapped to java
            // class
            mapper.disable(DeserializationFeature
                               .FAIL_ON_UNKNOWN_PROPERTIES);

            // mapper reading the json file and
            // deserializes it to employee object
            Employee emp = mapper.readValue(
                new File(
                    "/home/suchitra/Desktop/suchitra/projects/java-concurrency-examples/json-parsing/src/main/resources/emp1.json"),
                Employee.class);

            // Display message only
            System.out.println(
                "Reading values of employee attributes from a json file");

            // Print and display
            System.out.println(emp.toString());
        }

        // Catch block to handle exceptions

        // Catch block 1 to deal with json parsing exception
        catch (JsonParseException e) {
            e.printStackTrace();
        }

        // Catch block 2 to deal with json mapping exception
        catch (JsonMappingException e) {
            e.printStackTrace();
        }

        // Catch block 2 to deal with basic I/O exceptions
        catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

**输出:**

```java
Reading values of employee attributes from a json file
Employee [id=e01010, name=Jane, deptName=Sales, salary=100000.0]
```

**方法 2:** 在类级别提供注释@ JsonIgnoreProperties

另一种方法是在类级别@ JsonIgnoreProperties 提供注释(ignoreUnknown = true)。这个注释告诉 jackson 忽略那些不能映射到 java 类的属性。这与前面示例中的 emp1.json 相同。

```java
<u>emp1.json</u>
{"id":"e01010","name":"Jane","deptName":"Sales","salary":100000.0,"phoneNumber": 98218281812}
```

**例**

## 爪哇

```java
// Java Program to Remove UnrecognizedPropertyException by
// Providing an annotation at the class level
// @JsonIgnoreProperties

// Importing required classes
import com.fasterxml.jackson.annotation.JsonIgnoreProperties;
import java.io.*;

@JsonIgnoreProperties(ignoreUnknown = true)

// Class 1
// Helper class
public class Employee {

    // Member variables of this class
    private String id;
    private String name;
    private String deptName;
    private double salary;

    // Mamber functions of this class
    public String getId() { return id; }
    public void setId(String id) { this.id = id; }
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    public String getDeptName() { return deptName; }
    public void setDeptName(String deptName)
    {
        this.deptName = deptName;
    }
    public double getSalary() { return salary; }
    public void setSalary(double salary)
    {
        this.salary = salary;
    }
    @Override public String toString()
    {
        return "Employee [id=" + id + ", name=" + name
            + ", deptName=" + deptName
            + ", salary=" + salary + "]";
    }
}

// Class 2
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of ObjectMapper class
        ObjectMapper mapper = new ObjectMapper();

        // Try block to check for exceptions
        try {

            // Mapper reads from emp1.json and deserializes
            // it to employee object. It ignores those
            // properties which are not mapped to java class
            Employee emp = mapper.readValue(
                new File(
                    "/home/suchitra/Desktop/suchitra/projects/java-concurrency-examples/json-parsing/src/main/resources/emp1.json"),
                Employee.class);

            System.out.println(
                "Reading values of employee attributes from a json file");

            System.out.println(emp.toString());
        }

        // Catch block to handle the exceptions

        // Catch Block 1
        catch (JsonParseException e) {

            // Print the exception along wth line number
            // using printStackTrace() method
            e.printStackTrace();
        }

        // Catch Block 2
        catch (JsonMappingException e) {
            e.printStackTrace();
        }

        // Catch Block 3
        // Handling basic I/O exceptions
        catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

**输出:**

```java
Reading values of employee attributes from a json file
Employee [id=e01010, name=Jane, deptName=Sales, salary=100000.0]
```