# 用 Java | SQL 执行数据库操作创建、插入、更新、删除和选择

> 原文:[https://www . geesforgeks . org/performing-database-operations-Java-SQL-create-insert-update-delete-select/](https://www.geeksforgeeks.org/performing-database-operations-java-sql-create-insert-update-delete-select/)

本文将帮助您学习如何使用 JDBC (Java 数据库连接)API 进行基本的数据库操作。这些基本操作是 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 语言中的**插入、选择、更新和删除**语句。虽然目标数据库系统是 Oracle 数据库，但同样的技术也可以应用于其他数据库系统，因为所使用的查询语法是标准的 SQL，一般所有关系数据库系统都支持。
**先决条件:**

*   JDK
*   Oracle 数据库[(下载 Oracle 数据库快速版 11g 第 2 版)](http://www.oracle.com/technetwork/database/database-technologies/express-edition/downloads/index.html)
*   Oracle 数据库的 JDBC 驱动程序[(下载 Oracle 数据库 11g 第 2 版 JDBC 驱动程序)](http://www.oracle.com/technetwork/apps-tech/jdbc-112010-090769.html)。您需要将 *ojdbc6.jar* 添加到项目库中。

为了更好的理解，在继续之前，你需要浏览一下[这篇文章](https://www.geeksforgeeks.org/establishing-jdbc-connection-in-java/)文章。
**在甲骨文数据库中创建用户并授予所需权限:**

*   使用 cmd 打开 oracle。在 cmd 中键入 sqlplus，然后按回车键。
*   创建受密码保护的用户 id。该用户 id 称为子用户。

```
create user  identified by ;
```

*   向子用户授予所需的权限。为了简单起见，我们将数据库管理员权限授予子用户。

```
conn / as sysdba;
grant dba to ;
```

**创建带有空白字段的示例表:**

```
CREATE TABLE userid(
    id varchar2(30) NOT NULL PRIMARY KEY,
    pwd varchar2(30) NOT NULL,
    fullname varchar2(50),
    email varchar2(50)
);
```

**主要 JDBC 接口和类**

让我们概述一下 JDBC 的主要接口和类，我们将在本文中使用它们。它们都可以在 *java.sql* 包下获得:

*   **Class.forName() :** 这里我们在运行时将驱动程序的类文件加载到内存中。不需要使用新的或创建的对象。

```
Class.forName("oracle.jdbc.driver.OracleDriver");
```

*   **DriverManager:** 这个类用于注册特定数据库类型的驱动程序(例如本教程中的 Oracle Database)，并通过其 [**getConnection()**](https://practice.geeksforgeeks.org/problems/how-to-connect-to-a-database-in-java/) 方法与服务器建立数据库连接。
*   **连接:**这个接口代表一个已经建立的数据库连接(session)，我们可以从这个接口创建语句来执行查询和检索结果，获取关于数据库的元数据，关闭连接等。

```
Connection con = DriverManager.getConnection
("jdbc:oracle:thin:@localhost:1521:orcl", "login1", "pwd1");
```

*   **语句**和**编制报表**:这些接口分别用于执行静态 SQL 查询和参数化 SQL 查询。**报表**是**编制报表**界面的超级界面。他们常用的方法有:
    1.  **布尔执行(字符串 sql):** 执行一般的 sql 语句。如果查询返回*结果集*，则返回*真*，如果查询返回更新计数或不返回任何内容，则返回假。该方法只能与*语句*一起使用。
    2.  **int execute Update(String SQL):**执行 INSERT、UPDATE 或 DELETE 语句，并返回一个更新帐户，指示受影响的行数(例如，插入 1 行，或更新 2 行，或受影响 0 行)。

```
Statement stmt = con.createStatement();
      String q1 = "insert into userid values
      ('" +id+ "', '" +pwd+ "', '" +fullname+ "', '" +email+ "')";
      int x = stmt.executeUpdate(q1);
```

*   **结果集执行查询(字符串 sql):** 执行选择语句并返回一个*结果集*对象，该对象包含查询返回的结果。

```
Statement stmt = con.createStatement();
      String q1 = "select * from userid WHERE id = '" + id + "' 
      AND pwd = '" + pwd + "'";
      ResultSet rs = stmt.executeQuery(q1);
```

*   **结果集:**包含 SELECT 查询返回的表数据。使用 next()方法，使用此对象迭代结果集中的行。
*   **SQLException:** 这个被检查的异常被声明为被上面所有的方法抛出，所以我们在调用上面类的方法的时候必须要显式的捕捉这个异常。

**连接到数据库**

Oracle 数据库服务器监听位于*本地主机*的默认端口 *1521* 。以下代码片段通过用户 **login1** 和密码 **pwd1** 连接到数据库名称**用户标识**。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// Connecting to the Database
import java.sql.*;

public class connect
{
    public static void main(String args[])
    {
        try
        {
            Class.forName("oracle.jdbc.driver.OracleDriver");

            // Establishing Connection
            Connection con = DriverManager.getConnection(
             "jdbc:oracle:thin:@localhost:1521:orcl", "login1", "pwd1");

            if (con != null)            
                System.out.println("Connected");           
            else           
                System.out.println("Not Connected");

            con.close();
        }
        catch(Exception e)
        {
            System.out.println(e);
        }
    }
}
```

```
Output :
Connected
```

**注:**此处 ***oracle*** 在 getConnection()方法中的数据库 URL 中指定 Oracle Database 的 SID。对于 oracle 数据库 11g 是 ***orcl*** ，对于 Oracle 数据库 10g 是 ***xe*** 。

**执行插入语句**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// inserting to the Database
import java.sql.*;

public class insert1
{
    public static void main(String args[])
    {
        String id = "id1";
        String pwd = "pwd1";
        String fullname = "geeks for geeks";
        String email = "geeks@geeks.org";

        try
        {
            Class.forName("oracle.jdbc.driver.OracleDriver");
            Connection con = DriverManager.getConnection("
             jdbc:oracle:thin:@localhost:1521:orcl", "login1", "pwd1");
            Statement stmt = con.createStatement();

            // Inserting data in database
            String q1 = "insert into userid values('" +id+ "', '" +pwd+
                                  "', '" +fullname+ "', '" +email+ "')";
            int x = stmt.executeUpdate(q1);
            if (x > 0)           
                System.out.println("Successfully Inserted");           
            else           
                System.out.println("Insert Failed");

            con.close();
        }
        catch(Exception e)
        {
            System.out.println(e);
        }
    }
}
```

```
Output :
Successfully Registered
```

**实施更新声明**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// updating the Database
import java.sql.*;

public class update1
{
    public static void main(String args[])
    {
        String id = "id1";
        String pwd = "pwd1";
        String newPwd = "newpwd";
        try
        {
            Class.forName("oracle.jdbc.driver.OracleDriver");
            Connection con = DriverManager.getConnection("
             jdbc:oracle:thin:@localhost:1521:orcl", "login1", "pwd1");
            Statement stmt = con.createStatement();

            // Updating database
            String q1 = "UPDATE userid set pwd = '" + newPwd +
                    "' WHERE id = '" +id+ "' AND pwd = '" + pwd + "'";
            int x = stmt.executeUpdate(q1);

            if (x > 0)           
                System.out.println("Password Successfully Updated");           
            else           
                System.out.println("ERROR OCCURED :(");

            con.close();
        }
        catch(Exception e)
        {
            System.out.println(e);
        }
    }
}
```

```
Output :
Password Successfully Updated
```

**执行删除语句**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// deleting from Database
import java.sql.*;

public class delete
{
    public static void main(String args[])
    {
        String id = "id2";
        String pwd = "pwd2";
        try
        {
            Class.forName("oracle.jdbc.driver.OracleDriver");
            Connection con = DriverManager.getConnection("
             jdbc:oracle:thin:@localhost:1521:orcl", "login1", "pwd1");
            Statement stmt = con.createStatement();

            // Deleting from database
            String q1 = "DELETE from userid WHERE id = '" + id +
                    "' AND pwd = '" + pwd + "'";

            int x = stmt.executeUpdate(q1);

            if (x > 0)           
                System.out.println("One User Successfully Deleted");           
            else
                System.out.println("ERROR OCCURED :("); 

            con.close();
        }
        catch(Exception e)
        {
            System.out.println(e);
        }
    }
}
```

```
Output :
One User Successfully Deleted
```

**执行选择语句**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// selecting from Database
import java.sql.*;

public class select
{
    public static void main(String args[])
    {
        String id = "id1";
        String pwd = "pwd1";
        try
        {
            Class.forName("oracle.jdbc.driver.OracleDriver");
            Connection con = DriverManager.getConnection("
                    jdbc:oracle:thin:@localhost:1521:orcl", "login1", "pwd1");
            Statement stmt = con.createStatement();

            // SELECT query
            String q1 = "select * from userid WHERE id = '" + id +
                                    "' AND pwd = '" + pwd + "'";
            ResultSet rs = stmt.executeQuery(q1);
            if (rs.next())
            {
                System.out.println("User-Id : " + rs.getString(1));
                System.out.println("Full Name :" + rs.getString(3));
                System.out.println("E-mail :" + rs.getString(4));
            }
            else
            {
                System.out.println("No such user id is already registered");
            }
            con.close();
        }
        catch(Exception e)
        {
            System.out.println(e);
        }
    }
}
```

```
Output :
User-Id : id1
Full Name : geeks for geeks
E-mail :geeks@geeks.org
```

**注意:**这里的列索引是从 1 开始的，第一列会在索引 1，第二列在索引 2，以此类推。
对于其他数据类型，结果集提供了适当的获取方法:

*   获取弦 （）
*   getInt()
*   getFloat()
*   getDate（）
*   getTimestamp()
*   …..

本文由 [**Sangeet Anand**](https://www.linkedin.com/in/sangeet-anand-280365125/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。