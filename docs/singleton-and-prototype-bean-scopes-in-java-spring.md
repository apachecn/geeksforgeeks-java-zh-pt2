# Java Spring 中的单例和原型 Bean 范围

> 原文:[https://www . geesforgeks . org/singleton-and-prototype-bean-scopes-in-Java-spring/](https://www.geeksforgeeks.org/singleton-and-prototype-bean-scopes-in-java-spring/)

**Bean Scopes** 指的是 Bean 的生命周期，这意味着 Bean 的对象将在什么时候被实例化，该对象存在多长时间，以及将为该 Bean 创建多少个对象。基本上，它控制 bean 的实例创建，并由 spring 容器管理。
T3【春天的豆子范围】T5[春天的框架](https://www.geeksforgeeks.org/introduction-to-spring-framework/)为一个豆子提供了五个范围。我们只能在网页感知 **Spring ApplicationContext** 的上下文中使用其中的三个，其余两个都可以用于 **IoC 容器和 Spring-MVC 容器**。以下是为 bean 提供的不同范围:

1.  **Singleton:** 每个 Spring IoC 容器将只为单个 bean 定义创建一个实例，并且为该 bean 的每个请求共享相同的对象。
2.  **原型:**每次对单个 bean 定义发出请求时，都会为该 bean 定义创建一个新实例。
3.  **请求:**每次对单个 bean 定义发出 HTTP 请求时，都会为该 bean 定义创建一个新实例。但仅在网络感知的 Spring 应用程序上下文中有效。
4.  **会话:**将单个 bean 定义限定在一个 HTTP 会话的生命周期内。但仅在网络感知的 Spring 应用程序上下文中有效。
5.  **全局会话:**将单个 bean 定义限定到全局 HTTP 会话的生命周期。它也只在网络感知的 Spring ApplicationContext 上下文中有效。

让我们详细看看其中的一些:

### 单例范围:

如果作用域是单一的，那么每个 Spring IoC 容器将只实例化该 bean 的一个实例，并且每个请求将共享同一个实例。也就是说，当一个 bean 的范围被声明为 singleton 时，那么每当对该 bean 提出新的请求时，spring IOC 容器首先检查该 bean 的实例是否已经创建。如果它已经被创建，那么 IOC 容器返回相同的实例，否则它只在第一次请求时创建该 bean 的新实例。默认情况下，bean 的范围是单例的。
我们用一个例子来理解这个范围。

*   **步骤 1:** 让我们首先创建一个 bean(即)，它是 spring 框架中应用程序的主干。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate a bean
// created in the spring framework
package bean;

public class HelloWorld {
    public String name;

    // Create a setter method to
    // set the value passed by user
    public void setName(String name)
    {
        this.name = name;
    }

    // Create a getter method so that
    // the user can get the set value
    public String getName()
    {
        return name;
    }
}
```