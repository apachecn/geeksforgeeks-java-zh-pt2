# Java 中的移位运算符

> 原文:[https://www.geeksforgeeks.org/shift-operator-in-java/](https://www.geeksforgeeks.org/shift-operator-in-java/)

Java 中的运算符用于对变量和值执行操作。

**运算符示例:** +、-、*、/、> >、< <。

运算符类型:

*   Arithmetic operator,
*   Shift operator,
*   Relational operators,
*   Bitwise operator,
*   Logical operators,
*   Ternary operator sum
*   Assignment operator.

在本文中，我们将主要关注 Java 中的**移位运算符。**

通过将第一个操作数的位向右或向左移位，移位运算符对数据执行位操作。下面列出了 Java 编程语言中可用的移位运算符。shift 运算符是一个 java 运算符，用于向右或向左移动位模式。

### **Java 中移位运算符的类型:**

<figure class="table">

| 

**运算符名称**

 | **Symbol** | **Description** |
| --- | --- | --- |
| **Symbol shifts to the left** | < < | The left shift operator shifts to all the bits of the positioning number to the left. |
| **Signed right shift** | > > | The right shift operator shifts all bits to the right by a given number of bits. |
| **Unsigned right shift** | > > > | It is the same as signed right shift, but the leftmost empty space is filled with 0 instead of sign bit. |

</figure>

### **1。签名****Java 左移位运算符**

该运算符由符号<

**语法:**

```
left_operand  <<  number
```

**描述:**

如果 number=2，计算 number<<2 的值。

当一个数字的值向左移动两个位置时，最左边的两位就会丢失。该数字的值为 2。0010 是数字 2 的二进制表示。在以下示例中，解释了执行左移的方法:

在上面的例子中，二进制数 0010(十进制 2)在左移位(十进制 8)后变为 1000。

**示例:**

## Java

```
// Java program to demonstrate
// the Signed left shift operator
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        int number = 2;

          // 2 bit left shift operation
        int Ans = number << 2; 

        System.out.println(Ans);
    }
}
```

**输出**

```
8
```

### **2。Java 中带符号的右移位运算符**

右移运算符将数字的位向右移动给定的位数。>>符号表示右移位运算符，它被理解为大于的两倍。当您键入 x>>n 时，您告诉计算机将 x 位移动到正确的 n 个位置。

当我们向右移动一个数字时，最低有效位(最右边)被删除，符号位被填充在最重要的位置(最左边)。

**语法:**

```
left_operand  >>  number
```

**描述:**

如果 number=8，计算 number>>2 的值。

当一个数字的值向右移动两个位置时，最右边的两位就会丢失。该数字的值为 8。1000 是数字 8 的二进制表示。以下是如何执行右移的示例:

在上面的例子中，二进制数 1000(十进制 8)在向右移位(十进制 2)后变成 0010。

**示例:**

## Java

```
// Java program to demonstrate
// the Signed right shift operator
import java.io.*;

class GFG 
    {
    public static void main (String[] args) {
    {         
        int number = 8;

        // 2 bit signed right shift
        int Ans = number >> 2;

        System.out.println(Ans);    
    }
}
```

**输出**

```
2
```

### **3。Java 中的无符号右移位运算符**

无符号右移运算符将整数的位向右移动给定的位数。符号位用 0 填充。按位零填充右移位运算符由符号>>>表示。

**语法:**

```
left_operand  >>>  number
```

## Java

```
// Java program to demonstrate
// the Unsigned right shift operator
import java.io.*;

class GFG 
    {
    public static void main (String[] args) 
    {
        byte num1 = 8;
        byte num2 = -8;

        System.out.println(num1 >>> 2);    
        System.out.println(num2 >>> 2);    
    }
}
```

**输出**

```
2
1073741822
```

> **注意:**对于负位，有符号和无符号右移运算符提供不同的结果。

### **4。Java 中的无符号左移位运算符**

与无符号右移不同，Java 中没有“<