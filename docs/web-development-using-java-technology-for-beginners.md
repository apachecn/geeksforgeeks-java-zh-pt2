# 面向初学者的使用 Java 技术的 Web 开发

> 原文:[https://www . geesforgeks . org/web-开发-使用-Java-technology-for-初学者/](https://www.geeksforgeeks.org/web-development-using-java-technology-for-beginners/)

为了创建一个基于 java web 的项目，您可以按照下面解释的简单流程作为初学者创建一个项目。为了创建这样的 web 开发项目，geek 的第一步需要将有关 web 技术的知识移植到其他框架中。有很多方法可以创建这样的 Java web 项目，其中有很多框架 spring、maven、hibernate 等，这取决于项目的需求。对于一个天真的用户来说,[集合、框架](https://www.geeksforgeeks.org/java-collection-tutorial/)和[网络技术](https://www.geeksforgeeks.org/web-technology/)将会遗漏一些知识，但是，如果有人想要开发一个合适的 java 网络应用程序，那么如何进行下去的最起码的想法将需要至少一个技术组合来使用任何语言的清晰编程概念，最好是 java 或 python，因为现在大多数工具都是使用这些语言开发的。所以为了对抗这些语言现在是首选。

这里有一种方法或技术作为技术的组合，对于一个简单的 web 应用程序，只要对核心 java 有一点基础知识，并且对使用数据库的高级 java 有一点了解，就可以遵循这种方法或技术。为了创建一个项目，必须明确两端，这包括[前端和后端。](https://www.geeksforgeeks.org/frontend-vs-backend/)

1.  **前端**是指用户可以访问应用程序的部分。在 web 应用程序中，网页充当用户。在上述方法中，您将使用 JSP 和 HTML 页面。
2.  **后端**是指用户正在访问的页面，将通过需要开发的后端流程进行处理和控制。它也被称为“服务器端”，在这里完成数据记录、数据管理和逻辑控制。

> **现实情况**
> 
> 考虑一个购物中心的建筑，在这个建筑中，人们按照收到的指示，通过堆砌砖块作为单元来建造购物中心。这些人被称为前端构建者，而那些在稍后处理科学问题时在一张纸上布置布局以给基础提供最大稳定性的人被称为后端人员，该基础将被进一步包括在其上的研究和开发。这些人在做了研究、开发和测试后，向前端人员发出了指令。

现在回到项目，对于前端或者用户界面，你可以选择 [swing](https://www.geeksforgeeks.org/java-swing-jseparator-with-examples/) 或者 [JSP](https://www.geeksforgeeks.org/introduction-to-jsp/) 。这里以 JSP 作为示例部分，JSP 代表 Java 服务器页面

[JSP](https://www.geeksforgeeks.org/introduction-to-jsp/) 代表 Java 服务器页面。如果你了解 HTML、CSS，你就不会那么了解 JSP(一个 java 服务器页面)，在那里你只使用带有额外特性的 HTML 标签，而 JSP 就像一个动态网页。如果你想从一个更简单的方法开始，你也可以使用 HTML 页面来代替 JSP。

用户的输入可以用 JSP 通过*网页的形式收集，来自*数据库系统的记录可以分别以视图的形式出现。为了从数据库系统中检索包含数据的信息，使用了 JSP 的可用标签，这些标签用于不同的相关功能，如从一个页面到另一个页面，以及类似的其他方式**

****实现:**假设你有一个像表单字段一样的网页，在这个字段中输入的数据(用户输入的)将会在 Servlet 的帮助下被 java 编程访问。**

****示例:** [JSP](https://www.geeksforgeeks.org/introduction-to-jsp/) 页面有助于从数据库中检索信息并在网页上展示给用户。**

```
**login.jsp
<!DOCTYPE html>
<html>
<head>
<meta charset="ISO-8859-1">
                   <title>login here</title>
</head>
<body> 
            <form action="userlogin" method="post">
                               User Name <input type="text" name="username"><br>
                              Password <input type="password" name="password"><br>
                           <input type="submit" value="login">
           </form>
</body>
</html>**
```

**在上面的例子中，下面的标签是定义按钮提交后它将指向的 servlet 的动作。登录时的 Servlet 示例将在后半部分看到。**

****标签:****

```
**<form action="userlogin" method="post"> tag -> action** 
```

**[**【后端】**](https://www.geeksforgeeks.org/what-is-the-difference-between-front-end-and-back-end-web-development/) **:** 它确实涉及到一种编程语言，这里用 java 作为说明部分。**

**当你在 java 上做一个项目的时候，你应该有 java 的知识来处理逻辑，比如从数据库中获取数据，然后在 UI 部分发送回服务器等等，这是主要的后端部分，逻辑部分将在这里实现。**

**Java 将作为一种媒介，将 UI(需要了解 Servlet)和数据库(需要了解 JDBC)与其逻辑连接起来。人们必须为 java 安装 IDE，如 Eclipse 或 Netbeans 等。**

> ****注意:**如果在前端使用 Eclipse，使用 jsp 代替 swing 更好**

**[**【servlet】**](https://www.geeksforgeeks.org/introduction-java-servlets/)**是运行在支持 Java 的 web 服务器或应用服务器上的 Java 程序。它们用于处理从 web 服务器获得的请求，处理请求，生成响应，然后将响应发送回 web 服务器。虽然它是一个 java 类，但在 web 项目中是必需的。假设你有一个像表单域一样的网页，在这个域中输入的数据将在 Servlet 的帮助下被 java 编程访问。Servlet 有助于从网页重定向到 servlet，这些 servlet 类将有助于与其他 java 类连接。****

****servlet 中需要使用一些常见的函数:****

*   ****[*【get parameter()*](https://www.geeksforgeeks.org/getparameter-passing-data-from-client-to-jsp/)****
*   ****[*【getretdinspacher()*](https://www.geeksforgeeks.org/servlet-collaboration-java-using-requestdispatcher-httpservletresponse/)****
*   ****[*转发(请求、响应)*](https://www.geeksforgeeks.org/servlet-collaboration-java-using-requestdispatcher-httpservletresponse/)****

******实现:**这里使用的是 [HttpServlet 类](https://www.geeksforgeeks.org/the-httpsession-interface-in-servlet/)****

******示例:**是在如上图 JSP 页面示例的基础上提供的****

```
****// Importing required basic classes
import java.io.IOException;
import java.io.PrintWriter;
import java.util.Date;

// Importing classes from java.servlet package
// for connectivity of application class
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

// Since userlogin is used in action="userlogin"
// form tag in jsp page
@WebServlet("/userlogin")

// Class 1
// Helper class extending HttpServlet main class
**public class LoginServlet extends HttpServlet** 
**{**

    **// Method**
 **@Override**
 **protected void doPost(HttpServletRequest request,**
 **HttpServletResponse response)**
 **throws ServletException, IOException** 
 **{**

        response.setContentType("text/html");

        PrintWriter out = response.getWriter();

        // Customly setting name and password
        String name = request.getParameter("name");
        String password = request.getParameter("password");
        ....
        // Further programming
        // Code can be apppended here onward so
   ** }**
**}******
```

****[**【数据库】**](https://www.geeksforgeeks.org/dbms/) **:** 大多数网络应用程序都需要一个地方来存储使用哪个数据库的数据，例如，假设有一个网页注册为新用户。现在想想，这些数据都将保存在哪里？在这里，我们可以使用一个数据库来存储用户的数据，这个数据库可以随时访问。然而，这些数据将在用 java 编写的后端代码的帮助下被访问，并将与 UI 连接，正如 java 部分所解释的那样。****

****作为初学者，您应该使用关系数据库，您可以安装:****

*   ****关系型数据库****
*   ****神谕****

****[**【JDBC】**](https://www.geeksforgeeks.org/jdbc-drivers/)**:**如果你使用的是 java 和 MySQL 这样的数据库。由于不能直接使用 SQL 命令，您将如何与之通信？为此，您必须使用 JDBC(java 数据库连接)来连接数据库，并且必须使用一些抽象类，如 Connection 等。****

****这样，您就必须添加一个 jar 文件****

```
****For MySQL DB->mysql connector jar file and for**** 
```

```
****For Oracle->ojdbc jar file****
```

******实现:**连接类和应用程序(Main)类都在一个框架中表示如下，其中第一个框架是返回连接类对象的 JDBC 的连接类。第二帧表示相应连接类的应用程序类。****

******例******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
****// Java Program to Illustrate JDBC Connection In Oracle DB

// Importing database
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import oracle.jdbc.driver.OracleDriver;

// Class 1
// JDBC Connection Class
// To communicate with the database
// Note: This class is to be used in Application class
// where moto of this class is connection object
public class JDBCconnection {

    // Declaring connection class object and
    // initialiing it to null
    private static Connection connection = null;

    // Method
    // Static method that connects with database
    public static Connection getConnection()
    {

        // Try block to check for exceptions
        try {

            // Loading and registering drivers
            // using DriverManager

            // Setting instance as Oracle driver
            // This implies database is Oracle
            DriverManager.registerDriver(
                new OracleDriver());

            // Passing DB- URL,username,password
            connection = DriverManager.getConnection(
                "jdbc:oracle:thin:@localhost:1521:xe",
                "username", "password");
        }

        // Catch block ot handle DB exception
        catch (SQLException e) {

            // Display the line number where exception
            // occured using printStackTrace() method
            e.printStackTrace();
        }

        // If no exception cought database is connected
        return connection;

        // Display message successful connection
        System.out.print("Connection established");
    }
}****
```

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
****// Java Program to Illustrate JDBC Connection In SQL DB

// Importing database
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;

// Main class
// Application class
public class JdbcMySql {

    // Main driver method
    public static void main(String[] args)
    {

        // Try block to check for exceptions
        try {

            // Setting database type for connection as MYSQL
            Class.forName("com.mysql.jdbc.Driver");

            // Loading and registering driver

            // MYSQL database iul with DB
            // name, username and password
            Connection connection
                = DriverManager.getConnection(
                    "jdbc:mysql://localhost:3306/databaseName",
                    "username", "password");

            // If connection done with database this
            // staements will be printed otherwise exception
            // will be caught
            System.out.println("Connection established");

            // Closing the connections
            // using close() method
            connection.close();
        }
    }

    // Catch block to handle DB exceptions
    catch (SQLException e)
    {
        // Display the line number where exception occured
        e.printStackTrace();
    }
}****
```

******输出:**在控制台生成****

```
****Connection established**** 
```

****数据库连接后，您将使用一些常用功能:****

*   ****[createStatement()](https://www.geeksforgeeks.org/performing-database-operations-java-sql-create-insert-update-delete-select/) :返回语句对象****
*   ****[执行查询(查询)](https://www.geeksforgeeks.org/mitigation-sql-injection-attack-using-prepared-statements-parameterized-queries/):返回[结果集](https://www.geeksforgeeks.org/performing-database-operations-java-sql-create-insert-update-delete-select/)对象****
*   ****next()，getInt()，getString():结果集对象的方法****

****[**服务**](https://www.geeksforgeeks.org/difference-between-web-server-and-application-server/) **:** 对于你的应用，你需要一台服务器来托管。服务器运行 Java Servlets 您可以在 Java 中使用的简单而基本的服务器是 Tomcat。****

*   ****[**Tomcat**](https://www.geeksforgeeks.org/difference-between-apache-tomcat-server-and-apache-web-server/) 是一款网络服务器，旨在为本地系统的文件提供服务。****

> ****如果您使用的是 eclipse，那么您必须安装任何版本的 tomcat 服务器，并且需要添加应用程序的路径。然后，您可以使用 tomcat 提供的相应端口号轻松运行网页，Tomcat 将充当本地主机。****