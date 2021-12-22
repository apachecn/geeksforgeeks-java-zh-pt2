# 返回 Java 中的关键字

> 原文:[https://www.geeksforgeeks.org/return-keyword-java/](https://www.geeksforgeeks.org/return-keyword-java/)

在 Java 中， **return** 是一个保留的关键字，也就是我们不能把它作为标识符。它用于从方法中**退出**，有或没有值。**返回关键字**的用法有如下两种方式:

*   **情况 1:** 方法返回值
*   **情况 2:** 不返回值的方法

让我们通过直接实现它们来说明如下:

**情况 1:** 方法返回值

> 对于**定义了**返回类型的方法，返回语句**必须是紧接着返回值的**。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate Usage of return Keyword

// Main method
class GFG {

    // Method 1
    // Since return type of RR method is double
    // so this method should return double value
    double RR(double a, double b) {
        double sum = 0;
        sum = (a + b) / 2.0;

        // Return statement as we already above have declared
        // return type to be double
        return sum;
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Print statement
        System.out.println(new A().RR(5.5, 6.5));
    }
}
```

**Output**

```java
6.0
```

**输出解释:**当我们正在调用一个类 GFG 方法，该方法有**返回 sum** ，该方法返回 sum 的值，该值显示在控制台上。

**情况 2:不返回值的方法**

对于不返回值的方法，可以跳过 Java 中的 return 语句。这里出现了两种用户没有返回值的情况，如下所示:

*   **#1:** 方法在 void 函数中不使用 return 语句
*   **#2:** 返回式虚空**法**

**#1:** 方法在 void 函数中不使用 return 语句

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate no return
// keyword needed inside void method

// Main class
class GFG {

    // Since return type of RR method is
    // void so this method shouldn't return any value
    void demoSum(int a, int b)
    {
        int sum = 0;
        sum = (a + b) / 10;
        System.out.println(sum);

        // No return statement in this method
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Calling the method
        // Over custom inputs
        new GFG().demosum(5, 5);

        // Display message on the console for successful
        // execution of the program
        System.out.print(
            "No return keyword is used and program executed successfully");
    }

    // Note here we are not returning anything
    // as the return type is void
}
```

**Output**

```java
1
No return keyword is used and program executed successfully
```