# Java 中 StringBuffer delete()方法，带示例

> 原文:[https://www . geesforgeks . org/stringbuffer-delete-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuffer-delete-method-in-java-with-examples/)

java.lang.StringBuffer.delete()是 java 中的一个内置方法，用于移除或删除这个序列的子串中的字符。子字符串从指定的索引起点开始，延伸到索引终点的字符。
**语法:**

```
public StringBuffer delete(*int start_point, int end_point*)
```

**参数:**该方法接受两个整数类型的参数:
*start _ point*–这是指起始索引，包含在计数中。
*end _ point*–这是指结束索引，不包括在计数中。
**返回值:**该方法删除参数中提到的范围形成的子串后返回字符串。
**异常:**StringIndexOutOfBoundsException 如果*开始点*为负，大于长度()，或大于*结束点*，则发生异常。
**示例:**

```
Input: String = "Apple"
            start_point = 2 
            end_point = 4

Output: Ape

Input: String = "GeeksforGeeks"
       start_point = 2 
       end_point = 7

Output: GerGeeks
```

下面的程序说明了 java.lang.StringBuffer.delete()方法:
**程序 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// java.lang.StringBuffer.delete()
import java.lang.*;

public class geeks {

    public static void main(String[] args)
    {

        StringBuffer sbf = new StringBuffer("Geeksforgeeks");
        System.out.println("string buffer = " + sbf);

        // Deleting characters from index 2 to 7
        sbf.delete(6, 8);
        System.out.println("After deletion string buffer is = " + sbf);
    }
}
```

**Output:** 

```
string buffer = Geeksforgeeks
After deletion string buffer is = Geeksfgeeks
```