# 什么是爪哇 JDBC 的行集？

> 原文:[https://www.geeksforgeeks.org/what-is-rowset-in-java-jdbc/](https://www.geeksforgeeks.org/what-is-rowset-in-java-jdbc/)

RowSet 是 java.sql 包中存在的 java 接口。极客请注意不要将行集与结果集混淆。

> **注意:**行集存在于包 javax.sql 中，而 ResultSet 存在于包 java.sql 中

RowSet 的实例是 java bean 组件，因为它具有属性和 java bean 通知机制。在 JDK5 中有介绍。JDBC 行集提供了一种以表格形式存储数据的方法。它使数据比结果集更加灵活和容易。行集对象和数据源之间的连接在其整个生命周期中保持不变。

行集根据其实现方式分为五类，如下所示:

*   JdbcRowSet
*   CachedRowSet
*   网络浏览器
*   过滤器数据集
*   JoinRowSet

RowSet 的优势如下:

1.  Simple and flexible to use.
2.  The default is scrollable, the default is updatable, and the ResultSet can only be forwarded by default, and the read-only operation is only valid there.

JDBC 行集接口是行集扩展。它是 ResultSet 对象的包装器，增加了一些额外的特性。

**语法:**Jdbc 行集接口的声明

```
public interface JdbcRowSet
extends RowSet, Joinable
```

为了连接行集和数据库，行集接口提供了配置 Java bean 属性的方法，如下所示:

```
void setURL(String url):
void setUserName(String user_name):
void setPassword(String password):
```

最后，我们只需要创建一个 JdbcRowSet 对象，其中示例如下图所示:

**插图:**

```
JdbcRowSetrowSet = RowSetProvider.newFactory().createJdbcRowSet();

// 1\. Oracle database considered 
rowSet.setUrl("jdbc:oracle:thin:@localhost:1521:xe");

// 2\. username is set customly as - root 
rowSet.setUsername("root");

// 3\. Password is set customly as - pass
rowSet.setPassword("pass");

// 4\. Query 
rowSet.setCommand("select * from Students");
```

**实现:**假设我们在数据库中有一个名为**学生**的表，为:

```
+--------------+-------------+
|  RollNo |   Name   | Marks |
+--------------+-------------+
|    1    |   jack   |    92     |
|    2    |   jenny  |    90     | 
|    3    |   mark   |    80     |
|    4    |   joe    |    82     |
+--------------+-------------+
```

实现 JdbcRowSet 并检索记录

## 

```
// Java Program to Illustrate RowSet in JDBC

// Importing database
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.Statement;
import javax.sql.RowSetEvent;
import javax.sql.RowSetListener;
import javax.sql.rowset.JdbcRowSet;
import javax.sql.rowset.RowSetProvider;

// Main class
class RowSetDemo {

    // Main driver method
    public static void main(String args[])
    {

        // Try block to check for exceptions
        try {

            // Loading and registering drivers
            Class.forName(
                "oracle.jdbc.driver.OracleDriver");

            // Creating a RowSet
            JdbcRowSetrowSet = RowSetProvider.newFactory()
                                   .createJdbcRowSet();

            // Setting URL, username, password
            rowSet.setUrl(
                "jdbc:oracle:thin:@localhost:1521:xe");
            rowSet.setUsername("root");
            rowSet.setPassword("pass");

            // Creating a query
            rowSet.setCommand("select * from Student");

            // Executing the query
            rowSet.execute();

            // Processign the results
            while (rowSet.next()) {

                // Print and display commands
                System.out.println("RollNo: "
                                   + rowSet.getInt(1));
                System.out.println("Name: "
                                   + rowSet.getString(2));
                System.out.println("Marks: "
                                   + rowSet.getString(3));
            }
        }

        // Catch block to handle the exceptions
        catch (Exception e) {

            // Print and display the exception along with
            // line number using printStackTrace() method
            e.printStackTrace();
        }
    }
}
```

**输出:**

```
RollNo: 1
Name: jack 
Marks: 92
RollNo: 2
Name: jenny  
Marks: 90
RollNo: 3
Name: mark
Marks: 80
RollNo: 4
Name: joe
Marks: 82
```