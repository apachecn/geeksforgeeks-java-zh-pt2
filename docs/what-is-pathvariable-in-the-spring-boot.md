# Spring Boot 的路径变量是什么？

> 原文:[https://www . geesforgeks . org/什么是春季开机路径变量/](https://www.geeksforgeeks.org/what-is-pathvariable-in-the-spring-boot/)

Java 语言是所有编程语言中最流行的语言之一。使用 java 编程语言有几个优点，无论是出于安全目的还是构建大型分发项目。使用 Java 的优势之一是 JAVA 试图借助类、继承、多态等概念将语言中的每个概念与现实世界联系起来。

java 中还有其他几个概念可以增加 java 代码和程序员之间的用户友好交互，比如泛型、访问说明符、java 中的[注释](https://www.geeksforgeeks.org/annotations-in-java/)等。这些特性为 java 程序的类和方法增加了一个额外的属性。在本文中，我们将讨论什么是 spring boot 中的路径变量。

spring boot 中的 Path 变量借助@pathvariable 标注表示传入请求中不同种类的参数。

> **注意:**首先我们需要在我们的项目中建立 spring 应用。

[Spring Initializr](https://www.geeksforgeeks.org/spring-initializr/) 是一个基于 web 的工具，使用它我们可以很容易地生成 Spring Boot 项目的结构。它还为元数据模型中表达的项目提供了各种不同的特性。这个模型允许我们配置 JVM 支持的依赖列表。在这里，我们将使用 spring 初始化器创建应用程序的结构，然后使用 IDE 创建一个示例 GET 路由。因此，要做到这一点，需要遵循以下步骤:

**步骤 1:** 转到春季初始化

**第二步:**按要求填写详细内容。对于此应用:

```java
Project: Maven
Language: Java
Spring Boot: 2.2.8
Packaging: JAR
Java: 8
Dependencies: Spring Web
```

**第 3 步:**点击生成，将下载启动项目。

**第 4 步:**提取 zip 文件。现在打开一个合适的 IDE，然后转到文件- >新建- >来自现有来源的项目- > Spring-boot-app，并选择 pom.xml。单击提示符下的导入更改，等待项目同步，如下图所示:

![](img/938bf65050c80f1ce86dbf17ba3d2b23.png)

> **注意:**在 Maven 的导入项目窗口中，确保选择了与创建项目时选择的 JDK 相同的版本。

**第五步:**转到 src->main->java->com . gfg . spring . boot . app，创建一个名为 Controller 的 Java 类，并添加注释@RestController。现在创建一个 GET 应用编程接口，如下所示:

**例 1:**Controller.java

```java
@RestController

// Class
public class Controller {

    @GetMapping("/hello/{name}/{age}")

    public void insert(@PathVariable("name") String name,
                       @PathVariable("age") int age) {

        // Print and display name and age
        System.out.println(name);
        System.out.println(age);
    }
}
```

这个应用程序现在可以运行了。

**第 6 步:**运行 SpringBootAppApplication 类，等待 Tomcat 服务器启动。

![](img/093e5180d109d63d4fd76cdf5ca54c15.png)

> **注意:**Tomcat 服务器的默认端口是 8080，可以在 application.properties 文件中更改。

**第 7 步:**最后现在进入浏览器，输入网址 localhost:8080。观察输出，现在对 localhost:8080/hello/aayus/23 执行同样的操作

**输出:**

```java
Aayush
23
```