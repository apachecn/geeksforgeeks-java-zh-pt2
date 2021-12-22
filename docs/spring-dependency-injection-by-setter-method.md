# Spring–通过设置器方法进行依赖注入

> 原文:[https://www . geeksforgeeks . org/spring-dependency-injection-by-setter-method/](https://www.geeksforgeeks.org/spring-dependency-injection-by-setter-method/)

依赖注入是 Spring IOC(控制反转)提供的主要功能。Spring-Core 模块负责通过构造函数或 Setter 方法注入依赖关系。控制反转的设计原则强调保持 Java 类彼此独立，容器将它们从对象创建和维护中解放出来。这些由 Spring 管理的类必须遵守 Java-Bean 的标准定义。Spring 中的依赖注入也确保了类之间的松散耦合。

### 依赖注入的需求

假设类一需要类二的对象来实例化或操作一个方法，那么类一就被称为依赖于类二。虽然依赖另一个模块看起来没问题，但在现实世界中，这可能会导致很多问题，包括系统故障。因此，需要避免这种依赖性。Spring IOC 通过[依赖注入](https://www.geeksforgeeks.org/spring-dependency-injection-with-example/)解决了这样的依赖，使得代码更容易测试和重用。通过为公共功能定义接口，类之间的松散耦合是可能的，注入器将实例化所需实现的对象。实例化对象的任务由容器根据开发人员指定的配置来完成。

### 弹簧依赖注入的类型

有两种类型的 Spring 依赖注入。它们是:

*   **Setter 依赖注入(SDI):** 这是两种 DI 方法中比较简单的一种。在这种情况下，将在 setter 和/或 getter 方法的帮助下注入 DI。现在在 bean 中将 DI 设置为 SDI，这是通过 bean 配置文件完成的。为此，要用 SDI 设置的属性在 bean 配置文件中的<属性>标签下声明。
*   **构造函数依赖注入(CDI):** 在这种情况下，DI 将在构造函数的帮助下注入。现在在 bean 中将 DI 设置为 CDI，这是通过 bean 配置文件完成的。为此，要用 CDI 设置的属性在 bean 配置文件中的<构造函数-arg >标记下声明。

### **通过设置器方法进行依赖注入，示例**

Setter 注入是一种依赖注入，其中 spring 框架使用 setter 方法注入依赖对象。首先调用无参数构造函数，然后调用 setter 方法。它不会创建任何新的 bean 实例。让我们看一个通过 setter 方法注入依赖关系的例子。

1.  **Employee.java(POJO 级)**
2.  **config.xml**
3.  **Main.java**

**1。Employee.java 文件**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
package com.spring;

public class Student {

    private String studentName;
    private String studentCourse;

    public String getStudentName() 
    { 
      return studentName;
    }

    public void setStudentName(String studentName)
    {
        this.studentName = studentName;
    }

    public String getStudentCourse()
    {
        return studentCourse;
    }

    public void setStudentCourse(String studentCourse)
    {
        this.studentCourse = studentCourse;
    }

    @Override public String toString()
    {
        return "Student{"
            + "studentName=" + studentName + 
             ", studentCourse=" + studentCourse + '}';
    }
}
```

**2。配置 xml 文件**

## 可扩展标记语言

```java
<?xml version="1.0" encoding="UTF-8"?>
<beans 
 xmlns="http://www.springframework.org/schema/beans"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:context="http://www.springframework.org/schema/context"
 xsi:schemaLocation="http://www.springframework.org/schema/beans
                      https://www.springframework.org/schema/beans/spring-beans.xsd
                     http://www.springframework.org/schema/context
                      http://www.springframework.org/schema/context/spring-context.xsd">

     <bean class="com.springframework.Student" name="stud">

       <property name="studentName">
               <value> John </value> 
       <property/>

       <property name="studentCourse">
               <value> Spring Framework </value> 
          <property/>

    </bean>

</beans>
```

**3。Main.java 文件**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
package com.spring;

import java.io.*;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationCotenxt;

public class GFG {
    public static void main(String[] args)
    {
        ApplicationContext context = new ClassPathXmlApplicationCotenxt("config.xml");
        Student student= (Student)context.getBean("stud");
        System.out.println(student);
    }
}
```

**输出:**

```java
Student{ studentName= John  , studentCourse= Spring Framework }
```