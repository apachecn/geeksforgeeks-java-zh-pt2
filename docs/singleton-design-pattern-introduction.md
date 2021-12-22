# 单体设计模式|简介

> 原文:[https://www . geesforgeks . org/singleton-design-pattern-introduction/](https://www.geeksforgeeks.org/singleton-design-pattern-introduction/)

单件是**四人帮设计模式**的一部分，属于**创造**设计模式。在本文中，我们将深入研究 Singleton 模式的用法。就造型而言，这是最简单的设计模式之一，但另一方面，就使用的复杂性而言，这是最有争议的模式之一。

单例模式是一种设计模式，它限制一个类实例化它的多个对象。这只不过是定义一个类的一种方式。类的定义方式是，在程序或项目的完整执行过程中，只创建该类的一个实例。它用于只需要一个类实例来控制整个执行过程中的操作的情况。单例类在任何情况下都不应该有多个实例。单例类用于日志记录、驱动程序对象、缓存和线程池、数据库连接。

**单体设计模式**

![](img/47c49e897acb91876ea606412671d323.png)

**单例类的实现**

单例类的实现应该具有以下属性:

1.  **它应该只有一个实例:**这是通过从类内提供类的实例来实现的。应该防止外部类或子类创建实例。这是通过在 java 中使构造函数私有来实现的，这样没有类可以访问构造函数，因此不能实例化它。
2.  **实例应该是全局可访问的:**单例类的实例应该是全局可访问的，这样每个类都可以使用它。在 Java 中，这是通过公开实例的访问说明符来实现的。

```java
//A singleton class should have public visibility
//so that complete application can use
public class GFG {

  //static instance of class globally accessible
  public static GFG instance = new GFG();
  private GFG() {
    // private constructor so that class
    //cannot be instantiated from outside
    //this class
  }
}
```

**详细文章:** [在 Java 中实现单体设计模式](https://www.geeksforgeeks.org/singleton-design-pattern/)

**单例初始化类型**

*   **早期初始化:**在这个方法中，不管是否使用，类都会被初始化。这种方法的主要优点是简单。您可以在加载类时启动类。它的缺点是无论是否使用，类总是被初始化。*   **Lazy initialization :** In this method, class in initialized only when it is required. It can save you from instantiating the class when you don’t need it. Generally, lazy initialization is used when we create a singleton class.

    **Singleton 类示例**

    1.  **java.lang.Runtime :** Java 在其 lang 包中提供了一个类 Runtime，本质上是 singleton。每个 Java 应用程序都有一个类 Runtime 的实例，它允许应用程序与运行该应用程序的环境交互。当前运行时可以从 getRuntime()方法获得。
        应用程序无法实例化此类，因此无法为此类创建多个对象。因此运行时是一个单独的类。
    2.  **java.awt.Desktop :** The Desktop class allows a Java application to launch associated applications registered on the native desktop to handle a URI or a file.
        Supported operations include:
        *   启动用户默认浏览器以显示指定的 user
            启动用户默认邮件客户端，可选邮件发送到 URI；
        *   启动注册的应用程序来打开、编辑或打印指定的文件。
        *   这个类提供了对应于这些操作的方法。这些方法查找在当前平台上注册的相关应用程序，并启动它来处理 URI 或文件。如果没有关联的应用程序或者关联的应用程序无法启动，则会引发异常。
        *   每个操作都是由桌面表示的操作类型。动作类。

        此类也不能从应用程序实例化。因此它也是一个单独的类。

    **单例类的应用**

    单例模式有很多应用，比如缓存、数据库连接、驱动程序、日志。其中一些主要的是

    1.  **硬件接口访问:**单例的使用取决于需求。单例类也用于防止类的并发访问。实际上，在需要外部硬件资源使用限制的情况下，可以使用单一模式，例如硬件打印机，其中打印假脱机程序可以成为单一模式，以避免多个并发访问和创建死锁。
    2.  **记录器:**单例类用于日志文件生成。日志文件由 logger 类对象创建。假设一个应用程序，其中日志实用程序必须根据从用户那里收到的消息生成一个日志文件。如果有多个客户端应用程序使用此日志实用程序类，它们可能会创建此类的多个实例，这可能会在并发访问同一日志文件时导致问题。我们可以将 logger 实用程序类作为单例使用，并提供一个全局引用点，这样每个用户都可以使用这个实用程序，并且没有 2 个用户可以同时访问它。
    3.  **配置文件:**这是 Singleton 模式的另一个潜在候选，因为它具有性能优势，因为它可以防止多个用户重复访问和读取配置文件或属性文件。它创建配置文件的单个实例，可以由多个调用同时访问，因为它将提供加载到内存对象中的静态配置数据。应用程序仅第一次从配置文件中读取数据，此后从第二次调用开始，客户端应用程序从内存对象中读取数据。
    4.  **缓存:**我们可以将缓存用作单例对象，因为它可以有一个全局引用点，并且对于将来对缓存对象的所有调用，客户端应用程序都将使用内存中的对象。

    **重要点**

    *   单例类只能有一个实例，并且该实例应该是全局可访问的。
    *   java.lang.Runtime 和 java.awt.Desktop 是 JVM 提供的 2 个单体类。
    *   单一设计模式是一种创造性的设计模式。
    *   应该防止外部类创建单例类的实例。

    **进一步阅读:**[Python 中的单例模式](https://www.geeksforgeeks.org/singleton-pattern-in-python-a-complete-guide/)

    **参考文献:-**
    [【https://en.wikipedia.org/wiki/Singleton_pattern】](https://en.wikipedia.org/wiki/Singleton_pattern)
    [https://docs . Oracle . com/javase/7/docs/API/Java/lang/runtime . html](https://docs.oracle.com/javase/7/docs/api/java/lang/Runtime.html)
    [https://docs . Oracle . com/javase/7/docs/API/Java/awt/desktop . html](https://docs.oracle.com/javase/7/docs/api/java/awt/Desktop.html)

    本文由**维沙尔·加尔格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。