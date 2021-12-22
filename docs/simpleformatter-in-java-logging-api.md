# Java 日志 API 中的 SimpleFormatter

> 原文:[https://www . geesforgeks . org/simple formatter-in-Java-logging-API/](https://www.geeksforgeeks.org/simpleformatter-in-java-logging-api/)

日志对于任何软件应用程序都非常有用，它有助于发现项目在多个场景中的执行情况。在 Java 中， [java.util](https://www.geeksforgeeks.org/java-util-package-java/#:~:text=It%20contains%20the%20collections%20framework,the%20Important%20Classes%20in%20Java.) 包具有日志实用程序，下面的导入对于日志是非常必要的。

```java
import java.util.logging.ConsoleHandler;
import java.util.logging.FileHandler;
import java.util.logging.Handler;
import java.util.logging.Level;
import java.util.logging.LogManager;
import java.util.logging.Logger;
```

**通过属性文件显示日志消息的规范:**

在一个项目中，我们可以指定一个属性文件，它们可以跟踪日志记录功能的维护。其中“Java . util . logging . console handler . formatter”指定了要使用的 Formatter 类的名称，默认设置为**Java . util . logging . simple Formatter**，只不过是以纯文本显示日志条目。

## 爪哇

```java
// Specification of SimpleFormatter in .properties file
java.util.logging.ConsoleHandler.formatter
    = java.util.logging.SimpleFormatter

// Following are the different set of formats
// that are possible to give in the file We
// need to specify the format in a single line
// either like
java.util.logging.SimpleFormatter.format
    = [ % 1 $tF % 1 $tT ][% 4 $ - 7s] % 5 $s
      % n
// or
java.util.logging.SimpleFormatter.format
    = "%1$tc %2$s%n%4$s: %5$s%6$s%n"
```