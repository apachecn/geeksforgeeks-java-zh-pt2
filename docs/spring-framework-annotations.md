# 弹簧框架注释

> 原文:[https://www.geeksforgeeks.org/spring-framework-annotations/](https://www.geeksforgeeks.org/spring-framework-annotations/)

[Spring 框架](https://www.geeksforgeeks.org/introduction-to-spring-framework/)是最流行的 [Java EE 框架之一。](https://www.geeksforgeeks.org/difference-between-javaee-and-spring/)它是一个开源的轻量级框架，允许 Java EE 7 开发人员构建简单、可靠、可扩展的企业应用程序。这个框架主要侧重于提供各种方法来帮助您管理业务对象。现在谈谈 Spring Annotation，Spring Annotation 是一种元数据的形式，它提供了关于程序的数据。注释用于提供关于程序的补充信息。它对他们注释的代码的操作没有直接影响。它不会改变编译程序的动作。因此，在本文中，我们将通过一些示例来讨论 spring 框架中可用的主要注释类型。

**弹簧骨架标注类型**

基本上，在整个 spring 框架中有 6 种类型的注释。

1.  Spring heart annotation
2.  Spring net annotation
3.  Spring Boot 注解
4.  Annotations of spring scheduling
5.  Spring data annotation
6.  Spring bean annotation

**类型 1:** 弹簧芯注释

出现在***org . Spring framework . bean . factory . annotation***和***org . Spring framework . context . annotation***包中的 Spring 注释通常被称为 Spring Core 注释。我们可以把它们分为两类:

*   DI related notes
    *   @自动连线
    *   @ qualifier
    *   @初级
    *   @豆
    *   @懒惰
    *   @必选
    *   @值
    *   @作用域
    *   @查找等。
*   Context configuration comments
    *   @个人资料
    *   @导入
    *   @导入资源
    *   @属性源等。

**与依赖注入相关的注释**

**1.1:** @Autowired

@Autowired 注释应用于字段、setter 方法和构造函数。它隐式地注入对象依赖。我们使用@Autowired 来标记将由 Spring 容器注入的依赖项。

**1.2:** 场注

T5】爪哇

```java
class Student {
    @Autowired
    Address address;
}
```

**1.3:** 构造函数注入

## Java

```java
class Student {
    Address address;

    @Autowired
    Student(Address address) {
        this.address = address;
    }
}
```