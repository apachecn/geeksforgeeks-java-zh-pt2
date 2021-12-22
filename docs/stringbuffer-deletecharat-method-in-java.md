# Java 中 StringBuffer deleteCharAt()方法，带示例

> 原文:[https://www . geesforgeks . org/stringbuffer-delete charat-method-in-Java/](https://www.geeksforgeeks.org/stringbuffer-deletecharat-method-in-java/)

Java . lang . stringbuffer . delete charat()是一个内置的 Java 方法，它会移除序列中指定位置的字符。这样序列就减少了 1 个字符。

**语法:**

```
public StringBuffer deleteCharAt(*int indexpoint*)
```

**参数:**该方法接受整数类型的单个参数*索引点*，该索引点是指要删除的字符的索引。
**返回值:**该函数返回字符串或删除字符后返回该对象。
**异常:**如果索引点为负或者大于等于 length()，则该方法抛出*StringIndexOutOfBoundsException*。

**示例:**

```
Input : StringBuffer = worldofgeeks
        int indexpoint = 4
Output : worlofgeeks

```

以下程序说明了 StringBuffer.deleteCharAt()方法的工作:
**程序 1:**

```
// Java program to demonstrate working
// of StringBuffer.deleteCharAt() method

import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        StringBuffer sbf = new StringBuffer("raghav");
        System.out.println("String buffer before deletion = " + sbf);

        // Deleting the character at indexpoint 5
        sbf.deleteCharAt(5);
        System.out.println("After deletion new StringBuffer = " + sbf);
    }
}
```

**输出:**

```
String buffer before deletion = raghav
After deletion new StringBuffer = ragha
```

**程序 2:**

```
// Java program to demonstrate working
// of StringBuffer.deleteCharAt() method

import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        StringBuffer sbf = new StringBuffer("GeeksforGeeks");
        System.out.println("String buffer before deletion = " + sbf);

        // Deleting the character at indexpoint 5
        sbf.deleteCharAt(5);
        System.out.println("After deletion new StringBuffer = " + sbf);
    }
}
```

**输出:**

```
String buffer before deletion = GeeksforGeeks
After deletion new StringBuffer = GeeksorGeeks

```

**程序 3:**

```
// Java program to demonstrate working
// of StringBuffer.deleteCharAt() method

import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        StringBuffer sbf = new StringBuffer("Abhishek");
        System.out.println("String buffer before deletion = " + sbf);

        // Deleting the character at indexpoint -5
        sbf.deleteCharAt(-5);
        System.out.println("After deletion new StringBuffer = " + sbf);
    }
}
```

**输出:**

```
Exception in thread "main" java.lang.StringIndexOutOfBoundsException: 
                                             String index out of range: -5
    at java.lang.AbstractStringBuilder.deleteCharAt
                                          (AbstractStringBuilder.java:824)
    at java.lang.StringBuffer.deleteCharAt(StringBuffer.java:441)
    at Geeks.main(Geeks.java:14)
```