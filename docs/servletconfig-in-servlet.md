# Servlet

中的 ServletConfig

> 原文:[https://www.geeksforgeeks.org/servletconfig-in-servlet/](https://www.geeksforgeeks.org/servletconfig-in-servlet/)

**javax . servlet . servlet config**是作为 servlet API 一部分的接口。对于我们应用程序中的每个 Servlet 类，web 容器将创建一个 ServletConfig 对象，并且 web 容器将把这个对象作为参数传递给我们 Servlet 类对象的**公共 void init(Servlet config)**方法。servletConfig 上的一些要点是:

*   ServletConfig is an object containing some initial parameters or configuration information, which is created by the Servlet container and passed to the Servlet during initialization.
*   ServletConfig is specific to servlet, which means that servlet-specific information should be stored in web.xml and this object should be used to retrieve them.

### 例子

假设，一个人正在建立一个工作门户，并希望与招聘人员和求职者共享不同的电子邮件 id(可能会随着时间的推移而改变)。因此，他决定编写两个 servlets，一个用于处理招聘人员的请求，另一个用于求职者。

**在哪里存储电子邮件 id？**

将 email-id 作为不同 servlet 的名称-值对放入 web.xml 中，可以使用 getServletConfig()进一步检索。servlet 中的 getInitParameter(“名称”)。

### ServletConfig 接口中的方法

ServletConfig 界面

1.  **公共抽象 Java。朗。字符串 getServletName()**
2.  **菲兰达 javax 先生。servlet(servlet)。servletcontext getservletcontext()**
3.  **公共抽象 Java。朗。字符串 getInitParameter(Java。朗。字符串)**
4.  **公共抽象 Java。乌提尔。枚举<爪哇。朗。字符串> getnitparameternames()**

**1。公共抽象 Java . lang . string getServletName()**

在 web.xml 中配置 servlet 时，我们必须给 Servlet 起一个逻辑名称。假设我们有一个 Servlet 类 TestServlet，我们想在 **web.xml** 中配置它。

## XML

```
<web-app>
    <servlet>
        <servlet-name>Test</servlet-name>
        <servlet-class>TestServlet</servlet-class>
    </servlet>

    <servlet-mapping>
        <servlet-name>Test</servlet-name>
        <url-pattern>/test</url-pattern>
    </servlet-mapping>
</web-app>
```

在<servlet-name>中，我们已经为我们的 TestServlet 类给出了一个逻辑名称。因此，如果我们使用方法 getServletName()，它将返回 Servlet 的逻辑名称，在这种情况下，它将返回“Test”**。**</servlet-name>

**2。公共抽象 javax . servlet . servletcontext getServletContext()**

这个方法将简单地返回 ServletContext 对象。Web 容器为每个 web 应用程序创建一个 ServletContext 对象。

**3。公共抽象 Java . lang . string getInitParameter(Java . lang . string)**

我们可以将 init 参数存储为 web.xml 的一部分

## XML

```
<web-app>
   <servlet>
       <servlet-name>Test</servlet-name>
       <servlet-class>TestServlet</servlet-class>
       <init-param>
           <param-name>username</param-name>
           <param-value>xyz</param-value>
       </init-param>
 <init-param>
           <param-name>password</param-name>
           <param-value>welcome@123</param-value>
       </init-param>
   </servlet>

   <servlet-mapping>
       <servlet-name>Test</servlet-name>
       <url-apptern>/test</url-apptern>
   </servlet-mapping>
</web-app>
```

使用 init 参数的好处是我们不需要在源代码中硬编码值，如果我们不是在源代码中硬编码值，要改变值我们不需要接触源代码。我们只需要更改 web.xml 中的值并重新部署应用程序。这些初始化参数特定于您为其配置的 Servlet。通过使用 getInitParameter()，我们可以访问 Servlet 中 init 参数的值。

## 爪哇

```
import javax.servlet.Servlet;
import javax.servlet.ServletRequest;
import javax.servlet.ServletResponse;
import javax.servlet.ServletConfig;

public class TestServlet implements Servlet{
    private ServletConfig config;
     // web container will call this 
       // method by passing ServletConfig 
    public void init(ServletConfig config){
        this.config=config;
    }

    public void service(ServletRequest request, ServletResponse response){
        // pass <param-name> to get <param-value>
        String username=config.getInitParameter("username"); // xyz
        String password=config.getInitParameter("password"); // welcome@123
        System.out.println(username);
        System.out.println(password);

    }

    public void destroy(){

    }

    public ServletConfig getServletConfig(){
        return config;
    }

    public String getServletInfo(){
        return this.getClass().getName();
    }

}
```

**4。公共抽象 Java . util . enumeration<Java . lang . string>getInitParameterNames()**

此方法将返回包含所有初始化参数名称的枚举。