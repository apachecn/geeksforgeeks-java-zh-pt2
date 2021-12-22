# Spring Boot–代码结构

> 原文:[https://www.geeksforgeeks.org/spring-boot-code-structure/](https://www.geeksforgeeks.org/spring-boot-code-structure/)

Spring Boot 项目没有具体的布局或代码结构。然而，开发人员遵循的一些最佳实践也会对我们有所帮助。您可以将您的项目分为服务层、实体层、存储库层**、**等层。您也可以将项目分成模块。例如，父项目有两个子模块。第一个模块用于数据层，第二个模块用于 web 层。您也可以将项目划分为多个要素。

> **注意:**避免默认套餐

确实如此。因为当一个类不包含一个**包**声明时，它被认为是在一个**默认包**中。在默认包中包含类不是最佳做法。这是因为 Spring 扫描了注释中提到的包和子包中的类，如**@ components scan**、 **@EntityScan** 、**@ springootpapplication**等。

> **注意:**建议使用带有反向域名的 Java 的包命名约定。例如 **com.gfg.demo** 。

*   主应用程序类

建议将主应用程序类放在带有注释的根包中，如**@回弹应用程序**或**@组件扫描**或**@启用自动配置**。它允许 Spring 扫描根包和子包中的所有类。例如，如果您正在编写类似于下面布局示例中的 JPA 应用程序，MainApplicaiton.java 被放在根包中，所有与客户相关的类被放在子包 **com.gfg.demo.customer** 中，订单相关的类被放在 **com.gfg.demo.order** 中。

布局结构如下:

让我们讨论两种方法，大多数开发人员通常使用这两种方法来构建他们的 spring boot 项目。

1.  特征结构
2.  逐层结构

**结构 1:** 按特征

在这种方法中，与某个特性相关的所有类都放在同一个包中。以下示例显示了按特征外观划分的结构

**例**

```
com
 +- gfg
     +- demo
         +- MyApplication.java
         |
         +- customer
         |   +- Customer.java
         |   +- CustomerController.java
         |   +- CustomerService.java
         |   +- CustomerRepository.java
         |
         +- order
             +- Order.java
             +- OrderController.java
             +- OrderService.java
             +- OrderRepository.java
```

这种结构的优点如下:

*   找到一个要修改的类很容易。
*   通过删除特定的子包，可以删除与某个特性相关的所有类。
*   测试和重构很容易。
*   功能可以单独发货。

**结构 2:** 逐层

另一种放置类的方法是按层放置，即；所有控制器都可以放在控制器包和服务包下的服务以及域或模型等下的所有实体中。

**例**

```
com
 +- gfg
     +- demo
         +- MyApplication.java
         |
         +- domain
         |   +- Customer.java
         |   +- Order.java
         |
         +- controllers
         |     +- OrderController.java
         |   +- CustomerController.java
         |
         +- services
         |    +- CustomerService.java
         |    +- OrderService.java
         |
         +- repositories
              +- CustomerRepository.java
              +- OrderRepository.java    
```

虽然上面的结构看起来是可行的，并且很容易按层定位类。与按特征构造相比，它几乎没有缺点。

*   功能或模块不能单独发货。
*   很难找到属于某个特性的类。
*   某个要素的代码重构很困难，因为要素类位于每个图层中。
*   它会引起使用 [GitHub、BitBucket](https://www.geeksforgeeks.org/difference-between-bitbucket-and-github/) 等的开发者之间的合并冲突。为了合作。

现在让我们总结一下 MainApplication.java 的位置。在上面提出的两个结构中，我们已经看到**MainApplication.java**被放置在带有**@回弹应用**注释的根包中。如下面的示例所示，如下所示:

**例**

```
@SpringBootApplication
public class MyApplication {

    public static void main(String[] args) {
        SpringApplication.run(MyApplication.class, args);
    }

}
```