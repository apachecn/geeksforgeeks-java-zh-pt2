# 使用 Java 为 PDF 中的表格设置背景

> 原文:[https://www . geesforgeks . org/setting-background-to-a-table-in-pdf-use-Java/](https://www.geeksforgeeks.org/setting-background-to-a-table-in-a-pdf-using-java/)

你有没有想过 PDF 表格中不同的单元格是如何设置成各种颜色的？在本文中，我们将看到如何使用您最喜欢的语言 Java 中的 **iText** 库来设置 PDF 表格中各种单元格的背景。

**下载 iText**

创建一个新的 Java Maven 项目，并在 pom.xml 文件中添加以下依赖项。这一步将所有必需的 jar 文件添加到 Maven 依赖项中。

## XML

```java
<dependencies>       
      <dependency>         
         <groupId>com.itextpdf</groupId>         
         <artifactId>kernel</artifactId>         
         <version>7.0.2</version>     
      </dependency>  

      <dependency>         
         <groupId>com.itextpdf</groupId>         
         <artifactId>io</artifactId>         
         <version>7.0.2</version>     
      </dependency>  

      <dependency>         
         <groupId>com.itextpdf</groupId>         
         <artifactId>layout</artifactId>         
         <version>7.0.2</version>
      </dependency>  

      <dependency>         
         <groupId>com.itextpdf</groupId>         
         <artifactId>forms</artifactId>         
         <version>7.0.2</version>    
      </dependency>  

      <dependency>         
         <groupId>com.itextpdf</groupId>         
         <artifactId>pdfa</artifactId>         
         <version>7.0.2</version>     
      </dependency>  

      <dependency>         
         <groupId>com.itextpdf</groupId>         
         <artifactId>sign</artifactId>         
         <version>7.0.2</version>     
      </dependency>  

      <dependency>         
         <groupId>com.itextpdf</groupId>         
         <artifactId>barcodes</artifactId>         
         <version>7.0.2</version>     
      </dependency>  

      <dependency>         
         <groupId>com.itextpdf</groupId>         
         <artifactId>font-asian</artifactId>         
         <version>7.0.2</version>     
      </dependency>  

      <dependency>         
         <groupId>com.itextpdf</groupId>         
         <artifactId>hyph</artifactId>         
         <version>7.0.2</version>    
      </dependency> 
   </dependencies>
```