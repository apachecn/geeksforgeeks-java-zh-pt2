# 弹簧依赖注入示例

> 原文:[https://www . geeksforgeeks . org/spring-dependency-injection-with-example/](https://www.geeksforgeeks.org/spring-dependency-injection-with-example/)

**什么是依赖注入:**
依赖注入是 [Spring](https://www.geeksforgeeks.org/introduction-to-spring-framework/) IOC(控制反转)提供的主要功能。Spring-Core 模块负责通过构造函数或 Setter 方法注入依赖关系。控制反转的设计原则强调保持 Java 类彼此独立，容器将它们从对象创建和维护中解放出来。这些类由 [Spring](https://www.geeksforgeeks.org/introduction-to-spring-framework/) 管理，必须遵守 Java-Bean 的标准定义。 [Spring](https://www.geeksforgeeks.org/introduction-to-spring-framework/) 中的依赖注入也保证了类之间的松耦合。
**需要依赖注入:**
假设类一需要类二的对象来实例化或者操作一个方法，那么类一就被说成是**依赖类二**。现在，虽然一个模块依赖另一个模块看起来没问题，但是在现实世界中，这可能会导致很多问题，包括系统故障。因此，需要避免这种依赖性。
[Spring](https://www.geeksforgeeks.org/introduction-to-spring-framework/) IOC 通过依赖注入解决了这样的依赖，使得代码**更容易测试和重用**。通过为公共功能定义[接口](https://www.geeksforgeeks.org/interfaces-in-java/)，类之间的松散耦合是可能的，注入器将实例化所需实现的对象。实例化对象的任务由容器根据开发人员指定的配置来完成。
**弹簧依赖注入的类型:**
弹簧依赖注入有两种类型。它们是:

1.  **Setter 依赖注入(SDI)** :这是两种 DI 方法中比较简单的一种。在这种情况下，将在 setter 和/或 getter 方法的帮助下注入 DI。现在在 bean 中将 DI 设置为 SDI，这是通过 **bean 配置文件**完成的。为此，要用 SDI 设置的属性在 bean 配置文件中的 **<属性>** 标签下声明。
    **例:假设有一个 GFG 类使用 SDI，设置属性极客。下面给出了它的代码。**

## Java 语言(一种计算机语言，尤用于创建网站)

```
package com.geeksforgeeks.org;

import com.geeksforgeeks.org.IGeek;

public class GFG {

    // The object of the interface IGeek
    IGeek geek;

    // Setter method for property geek
    public void setGeek(IGeek geek)
    {
        this.geek = geek;
    }
}
```

1.  **在 bean-config 文件中设置 SDI:**

## 可扩展标记语言

```
<beans
xmlns="http://www.springframework.org/schema/beans"
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:schemaLocation="http://www.springframework.org/schema/beans
http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">

    <bean id="GFG" class="com.geeksforgeeks.org.GFG">
        <property name="geek">
            <ref bean="CsvGFG" />
        </property>
    </bean>

<bean id="CsvGFG" class="com.geeksforgeeks.org.impl.CsvGFG" />
<bean id="JsonGFG" class="com.geeksforgeeks.org.impl.JsonGFG" />

</beans>
```

1.  这在 setter 方法(“setGeek”)
    的帮助下将“CsvGFG”bean 注入到“GFG”对象中
2.  **构造函数依赖注入(CDI)** :在这种情况下，将借助[构造函数](https://www.geeksforgeeks.org/constructors-in-java/)注入 DI。现在在 bean 中将 DI 设置为 CDI，这是通过 **bean 配置文件**完成的，为此，要用 CDI 设置的属性在 bean 配置文件中的 **<构造函数-arg >** 标记下声明。
    **例:我们举一个和 SDI**
    一样的例子

## Java 语言(一种计算机语言，尤用于创建网站)

```
package com.geeksforgeeks.org;

import com.geeksforgeeks.org.IGeek;

public class GFG {

    // The object of the interface IGeek
    IGeek geek;

    // Constructor to set the CDI
    GFG(IGeek geek)
    {
        this.geek = geek;
    }
}
```

1.  **在 bean-config 文件中设置 CDI:**

## 可扩展标记语言

```
<beans
xmlns="http://www.springframework.org/schema/beans"
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:schemaLocation="http://www.springframework.org/schema/beans
http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">

    <bean id="GFG" class="com.geeksforgeeks.org.GFG">
        <constructor-arg>
            <bean class="com.geeksforgeeks.org.impl.CsvGFG" />
        </constructor-arg>
    </bean>

<bean id="CsvGFG" class="com.geeksforgeeks.org.impl.CsvGFG" />
<bean id="JsonGFG" class="com.geeksforgeeks.org.impl.JsonGFG" />

</beans>
```

1.  这将在构造函数的帮助下把“CsvGFG”bean 注入到“GFG”对象中。

**设置器依赖注入(SDI)与构造器依赖注入(CDI)**

<figure class="table">

| Setter DI | 构造函数 DI |
| --- | --- |
| Poor readability, because it adds a lot of boiler plate codes in application. | Very readable, because it appears in the code alone. |
| Bean must contain getter and setter methods of properties. | Clbeanss must declare a matching constructor with parameters. Otherwise, a BeanCreationException will be thrown. |
| You need to add the @Autowired annotation above the setter in the code, so it increases the coupling between the class and the DI container. | It is best to loosely couple with the DI container, because it doesn't even need to add @Autowired comments to the code. ( [Implicit constructor injection of single constructor scenario after Spring 4.0](https://spring.io/blog/2016/03/04/core-container-refinements-in-spring-framework-4-3) ) |
| Circular dependency or partial dependency arises from Setter DI, because object creation occurs before injection. | There is no scope for circular or partial dependency, because the dependency is solved before the object is created itself. |
| Preferred option when there are few properties and mutable objects can be created. | Preferred option when there are many attributes on the bean and immutable objects (such as financial process) are important to the application. |

</figure>

**春天 DI 的例子:**

*   我们使用了三个类和一个接口作为 beans 来举例说明 CDI 和 SDI 的概念。它们分别是车辆、丰田发动机、轮胎类和发动机接口。

*   从我们的例子中，我们可以看到 Vehicle 类依赖于 Engine 的实现，它是一个接口。(因此，基本上，汽车制造商想要符合印度排放标准的标准发动机。)类 ToyotaEngine 实现了接口，它的引用在映射到 Vehicle 类属性之一的 bean 配置文件中提供。

*   在 Vehicle 类中，我们调用应用程序上下文，并执行 bean 实例化。实例化了车辆类的两个对象。“obj1”是通过名为*的 bean injectwitconstructor*实例化的。bean 名称可以位于 bean 配置文件中。类似地,' obj2 '通过名为*注入器*的 bean 实例化。

*   可以观察到,“obj1”是通过构造函数注入的,“obj2”使用 setter 注入。

*   在下面的 bean 配置文件中，我们使用了两个 Vehicle beans 的声明。
*   *injectwitconstructor*bean 使用了元素构造函数-arg，带有属性名和 ref。“名称”属性与车辆类定义中给出的构造函数参数名称相关。而“ref”属性指向可以用于注入的 bean 引用。
*   *InjectwithSetter* 利用属性元素提供属性的“名称”和属性的“值”。可以用“ref”代替 value 属性来表示对 bean 的引用。
*   在配置细节中，我们将 ToyotaBean 引用注入到 Vehicle 类构造函数-arg 中的 ien engine 引用中，其中 ien engine 是一个接口，需要一个实现类引用来进行 Bean 注入。
*   我们为 Tyres 类使用了两个独立的 bean 引用，分别通过 setter 和构造函数注入。我们可以观察到“tyre1Bean”和“tyre2Bean”是用每个属性的字符串值初始化的。

<gfg-tab role="tab" slot="tab" id="gfg-tab-0">POM . XML</gfg-tab><gfg-panel role="tabpanel" slot="panel" id="gfg-panel-0" data-code-lang="XML"></gfg-panel>

```
 <dependencies>

    <!-- https:// mvnrepository.com/artifact
    /org.springframework/spring-core -->
    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-core</artifactId>
        <version>4.3.11.RELEASE</version>
    </dependency>

    <!-- https:// mvnrepository.com/artifact
    /org.springframework/spring-context -->
    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-context</artifactId>
        <version>4.3.11.RELEASE</version>
    </dependency>
</dependencies> 
```

<gfg-tab role="tab" slot="tab" id="gfg-tab-1">【enigne . Java</gfg-tab><gfg-tab role="tab" slot="tab" id="gfg-tab-2">【Toyota engine . Java</gfg-tab> <gfg-panel role="tabpanel" slot="panel" id="gfg-panel-2" data-code-lang="Java">```
 public class ToyotaEngine implements IEngine {
    String company;
    double cost;
    public double getCost()
    {
        return cost;
    }

    public void setCost(double cost)
    {
        cost = this.cost;
    }

    public String getCompany()
    {
        return company;
    }

    public void setCompany(String company)
    {
        this.company = company;
    }

    @Override
    public String importOrigin()
    {
        return "Japan";
    }

    @Override
    public double cost()
    {
        return cost;
    }
    @Override
    public String toString()
    {
        return "This is Engine object from: "
            + company;
    }
} 
```</gfg-panel>