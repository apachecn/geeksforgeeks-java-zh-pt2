# 弹簧–自动接线

> 原文:[https://www.geeksforgeeks.org/spring-autowiring/](https://www.geeksforgeeks.org/spring-autowiring/)

Spring 是 Java 的开源应用程序开发框架，允许您使用普通的旧 Java 对象(简称 **POJO** )创建健壮的企业应用程序。Spring 框架可以自动注入依赖关系。Spring 容器检测那些在配置文件中指定的依赖关系以及 beans 之间的关系。这在春季被称为自动布线。相比之下，自动连接的应用程序需要更少的代码行，但同时，它给程序员提供的灵活性很小。

### **自动接线模式**

自动布线有五种模式:

**1。否**

这种模式告诉框架，自动布线不应该完成。这是 Spring 使用的默认模式。

## 可扩展标记语言

```java
<bean id="state" class="sample.State">
 <property name="name" value="UP" />
</bean>
<bean id="city" class="sample.City"></bean>
```

**2。别名**

它使用 bean 的名称来注入依赖关系。但是，它要求属性和 bean 的名称必须相同。它在内部调用 setter 方法进行自动连接。

## XML

```java
<bean id="state" class="sample.State">
 <property name="name" value="UP" />
</bean>
<bean id="city" class="sample.City" autowire="byName"></bean>
```

**3 .by type〔t1〕**

它根据 bean 的类型注入依赖关系。它在配置文件中查找属性的类类型。如果它找到匹配的 bean，它将注入属性。如果没有，程序会抛出一个错误。在这种情况下，属性和 bean 的名称可以不同。它在内部调用 setter 方法进行自动连接。

## XML

```java
<bean id="state" class="sample.State">
 <property name="name" value="UP" />
</bean>
<bean id="city" class="sample.City" autowire="byType"></bean>
```

**4。建造师**

它通过调用构造函数注入所需的依赖关系。它的工作方式类似于“字节类型”模式，但它寻找构造函数参数的类类型。如果没有检测到或检测到一个以上的 bean，那么它会抛出一个错误，否则，它会在所有构造函数参数上自动连接“byType”。

## XML

```java
<bean id="state" class="sample.State">
 <property name="name" value="UP" />
</bean>
<bean id="city" class="sample.City" autowire="constructor"></bean>
```

**5。自动检测**

自动检测模式使用另外两种模式进行自动连接——构造函数和字节类型。它首先尝试通过构造函数模式自动连接，如果失败，它将使用字节类型模式进行自动连接。它在 Spring 2.0 和 2.5 中工作，但是从 Spring 3.0 开始就被弃用了。

## XML

```java
<bean id="state" class="sample.State">
 <property name="name" value="UP" />
</bean>
<bean id="city" class="sample.City" autowire="autodetect"></bean>
```

### **字节类型模式的示例程序**

**文件名:**T3】State.javaT5

T7】爪哇 T9

```java
public class State {
    private String name;
    public String getName() { return name; }
    public void setName(String s) { this.name = s; }
}
```

T10T12】

**文件名:**T3】City.javaT5

T7】爪哇 T9

```java
class City {
    private int id;
    private String name;
    private State s;
    public int getID() { return id; }
    public void setId(int eid) { this.id = eid; }
    public String getName() { return name; }
    public void setName(String st) { this.name = st; }
    public State getState() { return s; }
    @Autowired public void setState(State sta)
    {
        this.s = sta;
    }
    public void showCityDetails()
    {
        System.out.println("City Id : " + id);
        System.out.println("City Name : " + name);
        System.out.println("State : " + s.getName());
    }
}
```

T10T12】

**春豆配置文件:**

## XML

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
       xmlns:context="http://www.springframework.org/schema/context"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
       http://www.springframework.org/schema/beans/spring-beans.xsd
       http://www.springframework.org/schema/context
       http://www.springframework.org/schema/context/spring-context.xsd">
<bean id="state" class="sample.State">
<property name="name" value="UP" />
</bean>
<bean id="city" class="sample.City" autowire="byName"></bean>
</beans>
```

**测试程序文件:DemoApplication.java**

## 爪哇

```java
@SpringBootApplication
public class DemoApplication {
    public static void main(String[] args)
    {
        SpringApplication.run(DemoApplication.class, args);
        ApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");
        City cty = context.getBean("city", City.class);
        cty.setId(01);
        cty.setName("Varanasi");
        State st = context.getBean("state", State.class);
        st.setName("UP");
        cty.setState(st);
        cty.showCityDetails();
    }
}
```

**输出:**

```java
City ID : 01
City Name : Varanasi
State : UP
```

### 自动布线的优势

它需要更少的代码，因为我们不需要编写代码来显式地注入依赖关系。

### 自动布线的缺点

*   程序员无法控制。
*   它不能用于基元和字符串值。