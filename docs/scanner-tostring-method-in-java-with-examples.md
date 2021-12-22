# Java 中的 Scanner toString()方法，带示例

> 原文:[https://www . geesforgeks . org/scanner-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/scanner-tostring-method-in-java-with-examples/)

**[Java . util . Scanner](https://www.geeksforgeeks.org/scanner-class-in-java/)**类的 **toString()** 方法返回该 Scanner 的字符串表示形式。未指定确切的格式。

**语法:**

```java
public String toString()
```

**返回值:**该函数返回该扫描仪的**字符串表示**。

下面的程序说明了上面的功能:

**程序 1:**

```java
// Java program to illustrate the
// toString() method of Scanner class in Java

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        String s = "GeeksForGeeks - "
                   + "A Computer Science Portal for Geeks";

        // create a new scanner
        // with the specified String Object
        Scanner scanner = new Scanner(s);

        // print a line of the scanner
        System.out.println("Scanner String: \n"
                           + scanner.nextLine());

        // display information about this scanner
        System.out.println("\nString representation "
                           + "of this Scanner:\n"
                           + scanner.toString());

        // close the scanner
        scanner.close();
    }
}
```

**输出:**

```java
Scanner String: 
GeeksForGeeks - A Computer Science Portal for Geeks

String representation of this Scanner:
java.util.Scanner[delimiters=\p{javaWhitespace}+]
[position=51][match valid=true][need input=false]
[skipped=false][group separator=\,]
[decimal separator=\.][positive prefix=]
[negative prefix=\Q-\E][positive suffix=]
[negative suffix=][NaN string=\Q?\E][infinity string=\Q?\E]

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html # toString()](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html#toString())