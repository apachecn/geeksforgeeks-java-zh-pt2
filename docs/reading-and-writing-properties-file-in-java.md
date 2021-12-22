# 用 Java 读写属性文件

> 原文:[https://www . geesforgeks . org/读写属性-java 中的文件/](https://www.geeksforgeeks.org/reading-and-writing-properties-file-in-java/)

属性文件是我们在 Java 编程语言中用来保存配置参数的文件。我们称这些文件为资源包，因为它是我们将在应用程序中使用的资源包。

**配置参数有哪些？**

配置参数是您在配置数据库时使用的参数，或者项目中有任何验证，您可以将它们添加为配置参数。

**示例:**您一定在基于 Java 的 web 应用程序中使用了 **DBConnect** 类进行数据库连接。我们将所有的数据库 URL、数据库名称、数据库驱动程序都保存在这个类中。我们可以在 java 项目的资源文件夹中创建一个 **system.properties** 文件，而不是在这个类中编写这个配置参数。我们用于属性文件的扩展名是**。属性**。

**让我们看看属性文件:**

*   属性文件中的所有内容都以键值对的形式出现。
*   因此，为了访问该文件中的任何值，我们可以使用密钥

**为什么我们需要一个属性文件？**

您可以在没有属性文件的情况下工作，但是这样做的好处是，无论何时更改这个文件，您都不用担心编译问题。

假设您正在创建一个基于 Java web 的项目，因为您正在使用一些图像路径，并且该图像路径在项目的不同模块中使用。所以，如果你想改变路径中的某个东西，你必须在每个模块中改变它，而不是我们能做的，我们可以创建一个属性文件，因为我们可以在里面有图像路径的参数。所以，现在我们不需要改变每个模块。所以，这就是使用属性文件的好处。

**在这里，我们将创建我们的普通 jdbcmysql connection Class.java**

## Java 语言(一种计算机语言，尤用于创建网站)

```
package com.abc;

import java.sql.*;

public class DBConnect {

    public static Connection getConn()
    {
        Connection con = null;

        // driver name for mysql
        String loadDriver = "com.mysql.cj.jdbc.Driver";

        // url of the
        String dbURL = "jdbc:mysql://localhost:3306/DbName";
        // database

        // username to connect db
        String dbUSERNAME = "root";

        // password to connect db
        String dbPASSWORD = "root";

        try {
            // load the driver
            Class.forName(loadDriver);
            con = DriverManager.getConnection(
                dbURL, dbUSERNAME, dbPASSWORD);

            // get the connection
            Statement st = con.createStatement();
            ResultSet rs
                = st.executeQuery("SELECT * FROM CUSTOMER");
            while (rs.next()) {
                System.out.println(
                    "ID -" + rs.getInt(1) + " || "
                    + "First-Name -" + rs.getString(2)
                    + " || "
                    + "LastName -" + rs.getString(4));
            }
        }
        catch (ClassNotFoundException e) {
            // TODO Auto-generated catch block
            e.printStackTrace();
        }
        catch (SQLException e) {
            // TODO Auto-generated catch block
            e.printStackTrace();
        }

        return con; // return the connection obj.
    }
    public static void main(String[] args)
    {
        DBConnect.getConn();
    }
}
```

**输出:**

![](img/bc8841fe653ecdb277cee207915de8a8.png)

这是 Java 项目中的**DBConnect.java**文件。在这里，我们已经使用了这个类中的所有参数，因此，每当您的客户想要更改参数时，他/她必须转到这个文件，并相应地更改这些内容。但是相反，我们在这里可以做的是将所有这些配置参数保存在****system . properties**文件中。**

****让我们用 java 创建一个 system.properties 文件。****

***右键点击你的资源文件夹，创建一个属性文件。***

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
url=jdbc:mysql://localhost:3306/DBName
driver=com.mysql.cj.jdbc.Driver //Driver class of mysql
userName=root //Db username
password=root //Db password
```

**现在，如您所见，我们有一个属性文件，其中保存了所有这些参数，如网址、驱动程序、用户名和数据库密码。我们需要在您的 Java 类中访问这个属性文件。**

**让我们看看如何访问这个文件**

**我们必须使用 ResourceBundle 类，并且必须使用密钥进行访问。**

*   ****首先**，**我们将创建资源包的对象，并将属性文件名传递给它。****
*   ****接下来，我们要用 getString(key)方法来调用这个值。****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
package com;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.util.ResourceBundle;

public class DBConnect {

    public static Connection getConn()
    {
        ResourceBundle rd
            = ResourceBundle.getBundle("system");
        Connection con = null;

        // driver name for mysql
        String loadDriver = rd.getString("driver");

        // url of the database
        String dbURL = rd.getString("url");

        // username to connect db
        String dbUSERNAME = rd.getString("userName");

        // password to connect db
        String dbPASSWORD = rd.getString("password");

        try {
            // load the driver
            Class.forName(loadDriver);

            // get the connection
            con = DriverManager.getConnection(
                dbURL, dbUSERNAME, dbPASSWORD);
            Statement st = con.createStatement();
            ResultSet rs
                = st.executeQuery("SELECT * FROM CUSTOMER");
            while (rs.next()) {
                System.out.println(
                    "ID -" + rs.getInt(1) + " || "
                    + "First-Name -" + rs.getString(2)
                    + " || "
                    + "LastName -" + rs.getString(4));
            }
        }
        catch (ClassNotFoundException e) {
            // TODO Auto-generated catch block
            e.printStackTrace();
        }
        catch (SQLException e) {
            // TODO Auto-generated catch block
            e.printStackTrace();
        }

        return con;
    }
    public static void main(String[] args)
    {
        DBConnect.getConn();
    }
}
```

****输出:****

**![](img/bc8841fe653ecdb277cee207915de8a8.png)**