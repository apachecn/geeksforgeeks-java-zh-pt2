# Java 中的 var 关键字

> 原文:[https://www.geeksforgeeks.org/var-keyword-in-java/](https://www.geeksforgeeks.org/var-keyword-in-java/)

在 Java 10 中引入了 **var** 关键字。类型推断在 var 关键字中使用，它根据周围的上下文自动检测变量的数据类型。下面的例子解释了在哪里使用 **var** 以及在哪里不能使用它。

**1。我们可以用** **var 关键字声明任何数据类型。**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to explain that
// var can used to declare any datatype

class Demo1 {

    public static void main(String[] args)
    {

        // int
        var x = 100;

        // double
        var y = 1.90;

        // char
        var z = 'a';

        // string
        var p = "tanu";

        // boolean
        var q = false;

        // type inference is used in var keyword in which it
        // automatically detects the datatype of a variable
        System.out.println(x);
        System.out.println(y);
        System.out.println(z);
        System.out.println(p);
        System.out.println(q);
    }
}
```

**Output**

```java
100
1.9
a
tanu
false
```

**2。var 可以用在局部变量声明中。**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate that
// var can be used to declare a local variable

class Demo2 {
    public static void main(String[] args)
    {

        // local variable
        var x = 100;

        // print x to the console
        System.out.println(x);
    }
}
```

**Output**

```java
100
```

**3。var 不能用在实例和全局变量声明中。**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate that
// var cannot be used to declare
// instance and global variables

class Demo3 {

    // instance variable
    var x = 50;
    public static void main(String[] args)
    {
        System.out.println(x);
    }
}
```

**输出**

```java
prog.java:8: error: 'var' is not allowed here
    var x = 50;
    ^
1 error
```

**4。变量不能用作泛型类型。**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate that
// var cannot be used as a Generic
// type

import java.util.*;
class Demo4 {
    public static void main(String[] args)
    {
          // Generic list using var
        var<var> al = new ArrayList<>();

          // add elements
        al.add(10);
        al.add(20);
        al.add(30);

        // print the list
        System.out.println(al);
    }
}
```

**输出**

```java
prog.java:10: error: 'var' is not allowed here
        var<var> al = new ArrayList<>();
            ^
1 error
```

**5。var 不能与泛型类型一起使用。**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate that
// var cannot be used with Generic type

import java.util.*;
class Demo5 {
    public static void main(String[] args)
    {
          // var used with Generic type
        var<Integer> al = new ArrayList<Integer>();

          // add elements 
        al.add(10);
        al.add(20);
        al.add(30);

        // print the list
        System.out.println(al);

          // This is valid since type is decided
          // based on ArrayList<String>
          var list = new ArrayList<String>();
    }
}
```

**输出**

```java
prog.java:9: error: illegal reference to restricted type 'var'
        var<Integer> al = new ArrayList<Integer>();
        ^
1 error
```

**6。没有显式初始化，就不能使用 var。**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate that
// var cannot be used without explicit
// initialization

import java.io.*;

class Demo6 {
    public static void main(String[] args)
    {

        // declaration without
        // initialization
        var variable;

          // This is also not valid
        var variable = null;
    }
}
```

**输出**

```java
prog.java:13: error: cannot infer type for local variable variable
        var variable;
            ^
  (cannot use 'var' on variable without initializer)
prog.java:16: error: cannot infer type for local variable variable
        var variable = null;
            ^
  (variable initializer is 'null')
2 errors
```

**7。var 不能与 Lambda 表达式一起使用。**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate that
// var cannot be used with Lambda
// Expression

import java.util.*;

interface myInt {

    int add(int a, int b);
}
class Demo7 {
    public static void main(String[] args)
    {

          // var cannot be used since they
          // require explicit target type
        var obj = (a, b) -> (a + b);

          // calling add method
        System.out.println(obj.add(2, 3));
    }
}
```

```java
prog.java:13: error: cannot infer type for local variable obj
          var obj = (a, b) -> {
              ^
  (lambda expression needs an explicit target-type)
1 error
```

**8。var 不能用于方法参数和返回类型。**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to explain that
// var cannot be used for a method
// parameters and return type

class Demo8 {

    // method1 using var
    // as a return type
    var method1() { return ("Inside Method1"); }

    // method2 using var for a
    // parameter
    void method2(var a) { System.out.println(a); }

    public static void main(String[] args)
    {

        // create an instance
        Demo1 obj = new Demo1();

        // call method1
        var res = obj.method1();

        // call method2
        obj.method2();
    }
}
```

**输出**

```java
prog.java:6: error: 'var' is not allowed here
    var method1()
    ^
prog.java:11: error: 'var' is not allowed here
    void method2(var a)
                 ^
2 errors
```