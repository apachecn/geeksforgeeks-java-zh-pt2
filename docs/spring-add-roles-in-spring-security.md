# Spring–在 Spring Security 中添加角色

> 原文:[https://www . geesforgeks . org/spring-add-roles-in-spring-security/](https://www.geeksforgeeks.org/spring-add-roles-in-spring-security/)

**Spring Security** 是一个功能强大且高度可定制的身份验证和访问控制框架。这是保护基于 Spring 的应用程序的事实标准。Spring Security 是一个专注于为 Java 应用程序提供身份验证和授权的框架。与所有 Spring 项目一样，Spring Security 的真正威力在于它可以轻松扩展以满足定制需求。Spring Security 的一些关键特性包括:

1.  对身份验证和授权的全面和可扩展的支持
2.  防止像会话固定、点击劫持、跨站点请求伪造等攻击
3.  Servlet 应用编程接口集成
4.  与 Spring Web MVC 的可选集成

在本文中，我们将讨论如何在 spring security 中添加角色。几乎在每一个网络应用程序中，我们做的第一步是认证，这是每个想要访问网络应用程序但考虑到学生和教师都在使用该网站的大学应用程序的人的第一个主要步骤。所有的老师都有额外的权限，比如他们可以删除特定学生的记录，但是学生不能这样做。现在想想这怎么可能？只有当角色不同时，这才是可能的/删除请求只能由高优先级角色发出，而不能由低优先级角色发出。在这种情况下，学生被设定为低优先级角色，而教师被设定为高优先级角色。让我们讨论如何在 spring web 应用程序中添加角色。

### **分步实施**

**第一步:转到弹簧初始化器**

按照要求填写细节。对于此应用:

```
Project: Maven
Language: Java
Spring Boot: 2.2.8
Packaging: JAR
Java: 8
Dependencies: Spring Web
```

![](img/56491d5b07a7b31cc96ea9c9aeadbeef.png)

**第 2 步:**点击生成，将下载启动项目。

**第三步:**提取 zip 文件。现在打开一个合适的 IDE，然后转到**文件>从现有资源>新建>项目春季启动应用程序，并选择 pom.xml** 。点击提示中的导入更改，等待项目同步，如下图所示:

![](img/938bf65050c80f1ce86dbf17ba3d2b23.png)

> **注意**:在 Maven 的导入项目窗口中，确保选择了创建项目时选择的相同版本的 JDK。

**第四步:**现在进入 src >主界面>java>com . gfg . spring . boot . app，创建两个 Java 文件一个是**controller.java**另一个是**config.java**

**controller.java**

## Java 语言(一种计算机语言，尤用于创建网站)

```
@RestController
public class controller {

    @GetMapping("/delete") public String delete()
    {
        return "This is the delete request";
    }
}
```