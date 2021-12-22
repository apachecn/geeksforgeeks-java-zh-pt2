# Java 中的 i++和++i 有什么区别？

> 原文:[https://www . geesforgeks . org/Java 中的 I 和 I 的区别是什么/](https://www.geeksforgeeks.org/what-is-the-difference-between-i-and-i-in-java/)

++i 和 i++都将 **i** 的值增加 1，但方式不同。如果 **++** 在变量之前，它被称为前增量运算符，在变量之后，它被称为后增量运算符。

java 中的增量有两种执行方式，

1) **后递增(i++):** 如果要使用当前值，我们在语句中使用 i++，然后要将 **i** 的值递增 1。

2) **预增量(++i)** :如果我们想将 **i** 的值增加 1，然后在我们的语句中使用它，我们在语句中使用++i。

**例**

```java
int i = 3;
int a = i++; // a = 3, i = 4
int b = ++a; // b = 4, a = 4
```

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate pre and post increment
// operators

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // initialize i
        int i = 0;
        System.out.println("Post-Increment");

        // i values is incremented to 1 after returning
        // current value i.e; 0
        System.out.println(i++);

        // initialized to 0
        int j = 0;
        System.out.println("Pre-Increment");

        // j is incremented to 1 and then it's value is
        // returned
        System.out.println(++j);
    }
}
```

**Output**

```java
Post-Increment
0
Pre-Increment
1
```

**示例 2:** 无法对常数值应用增量运算符(++)

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Applying increment operator on a constant value

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        int x = ++10;

        System.out.println("Hello");
    }
}
```

**输出**

```java
prog.java:8: error: unexpected type
          int x = ++ 10;
                     ^
  required: variable
  found:    value
1 error
```