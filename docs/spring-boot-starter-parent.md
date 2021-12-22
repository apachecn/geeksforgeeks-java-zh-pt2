# Spring Boot–起始母公司

> 原文:[https://www.geeksforgeeks.org/spring-boot-starter-parent/](https://www.geeksforgeeks.org/spring-boot-starter-parent/)

Spring Boot Starter Parent 是一个为基于 Spring 的应用程序提供默认配置的 Starter 项目。它作为父级添加到 pom.xml 文件中。**弹簧靴启动器父级**将**弹簧靴依赖项**定义为其父级。**春季开机启动器父项**继承了**春季开机依赖项**的依赖项管理。每个 Spring Boot 版本都提供了一个依赖列表和它支持的最新版本。starter parent 的依赖项管理特性允许公共依赖项省略 pom.xml 文件中的 **<版本>** 标记。如果一个依赖项需要一个特定的版本，而不是由起始父项配置的版本，那么可以使用 **<版本>** 标签添加该版本。以下是起始父项目的特性:

*   The dependency management feature manages the versions of public dependencies.
*   Provide source code encoding with default compiler levels of Java 1.8 and UTF-8.
*   为专家插件提供默认配置,如 maven-surefire-plugin、maven-jar-plugin 和 maven-故障安全插件.
*   Use **repackaging execution ID** to execute **repackaging** target.
*   Resource filtering and configuration profile specific files.

**的父代**看起来如下

```java
<parent>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-dependencies</artifactId>
    <version>2.1.0.RELEASE</version>
    <relativePath>../../spring-boot-dependencies</relativePath>
</parent>
```

必须在 pom.xml 中添加以下代码，以使用**spring-boot-starter-parent**作为父项目。

```java
<parent>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-parent</artifactId>
    <version>2.5.2</version> <!-- spring boot version number -->
    <relativePath/> <!-- lookup parent from repository -->
</parent>
```

**管理依赖关系**

任何弹簧靴启动器都可以包含在**依赖项**部分中。如果我们省略了特定初学者的版本，Maven 将根据在**父级**部分定义的版本号下载 jar 文件。例如，如果我们需要一个数据访问层，那么我们应该在 pom.xml 文件中添加 **spring-data-jpa** 依赖启动器。

```java
<dependencies>
  <dependency>
    <groupId>org.springframework.data</groupId>
    <artifactId>spring-data-jpa</artifactId>
  </dependency>
<dependencies>
```

**依赖关系管理标签**

如果您需要由**spring-boot-starter-parent**提供的不同版本的依赖项，我们可以在 **<版本></版本>** 标签中添加特定版本，并将依赖项及其版本包含在 **dependencyManagement** 部分中。

```java
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
            <version>2.4.0</version>
        </dependency>
    </dependencies>
</dependencyManagement>
```

**属性**

我们知道**spring-boot-starter-parent**使用其中定义的属性来配置 java 编译器版本、Maven 插件版本和 Dependencies 版本。我们可以在**属性**部分覆盖 pom.xml 文件中的那些属性值。假设我们的项目需要不同版本的 **sl4j** 库和不同的 java 版本。

```java
<properties>
    <java.version>1.8</java.version>
    <slf4j.version>1.7.30</slf4j.version>
</properties>
```

**使用没有初始家长的 Spring Boot**

如果我们想从自定义父 POM 继承或者手动定义所有 Maven 配置，我们不会从**spring-boot-starter-parent**POM 继承。但是，我们仍然可以从**春季启动依赖项**提供的依赖项管理功能(不是插件管理)中受益，通过将依赖项包含在**依赖项**部分中作为导入范围。

```java
<dependencyManagement>
    <dependencies>
        <dependency>
            <!-- Import dependency management from Spring Boot -->
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-dependencies</artifactId>
            <version>2.5.2</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencies>
</dependencyManagement>
```

> **注意:**要覆盖单个依赖项的属性，我们需要在添加**spring-boot-dependencies**之前添加那些依赖项。