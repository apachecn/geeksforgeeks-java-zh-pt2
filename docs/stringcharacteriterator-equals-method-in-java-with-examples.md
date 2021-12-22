# Java 中 StringCharacterIterator()方法，示例

> 原文:[https://www . geeksforgeeks . org/stringcharacterterator-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringcharacteriterator-equals-method-in-java-with-examples/)

**等于()**的**法。Java 中的 stringcharacteriaterter 类**用于检查这个 stringcharacteriaterter 与指定的 stringcharacteriaterter 是否相等。该方法获取一个 stringcharacterTerrar 实例，并将其与该 stringcharacterTerrar 进行比较，然后返回一个表示相同内容的布尔值。

**语法:**

```java
public boolean equals(Object obj)

```

**参数:**该方法接受一个参数**对象**，该参数是要检查是否与该字符串特征符相等的字符串特征符。

**返回值:**这个方法返回一个**布尔**，告诉这个字符串特征符是否等于指定的对象。

**异常:**这个方法不抛出任何异常。

**程序:**

```java
// Java program to demonstrate
// the above method

import java.text.*;
import java.util.*;

public class StringCharacterIteratorDemo {
    public static void main(String[] args)
    {

        StringCharacterIterator sci1
            = new StringCharacterIterator(
                "GeeksforGeeks");

        System.out.println("StringCharacterIterator 1: "
                           + sci1);

        StringCharacterIterator sci2
            = new StringCharacterIterator(
                "Geeks for Geeks");

        System.out.println("StringCharacterIterator 2: "
                           + sci2);

        StringCharacterIterator sci3
            = (StringCharacterIterator)sci1
                  .clone();

        System.out.println("StringCharacterIterator 3: "
                           + sci3);

        System.out.println("Comparing DFS 1 and DFS 2: "
                           + sci1.equals(sci2));

        System.out.println("Comparing DFS 2 and DFS 3: "
                           + sci2.equals(sci3));

        System.out.println("Comparing DFS 1 and DFS 3: "
                           + sci1.equals(sci3));
    }
}
```

**输出:**

```java
StringCharacterIterator 1: java.text.StringCharacterIterator@bd43b778
StringCharacterIterator 2: java.text.StringCharacterIterator@ac5740a8
StringCharacterIterator 3: java.text.StringCharacterIterator@bd43b778
Comparing DFS 1 and DFS 2: false
Comparing DFS 2 and DFS 3: false
Comparing DFS 1 and DFS 3: true

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/stringcharacterterator . html # equals-Java . lang . object-](https://docs.oracle.com/javase/9/docs/api/java/text/StringCharacterIterator.html#equals-java.lang.Object-)