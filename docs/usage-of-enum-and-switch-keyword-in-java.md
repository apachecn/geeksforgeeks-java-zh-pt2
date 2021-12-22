# 枚举和 Switch 关键字在 Java 中的用法

> 原文:[https://www . geeksforgeeks . org/use-of-enum-and-switch-关键字 in-java/](https://www.geeksforgeeks.org/usage-of-enum-and-switch-keyword-in-java/)

An [**Enum**](https://www.geeksforgeeks.org/enum-in-java/) 是 java 中一种独特的数据类型，通常是常量的**集合(集合)。更具体地说，Java 枚举类型是一种独特的 Java 类。枚举可以保存常量、方法等。一个 Enum 关键字可以和 if 语句、switch 语句、迭代等一起使用。**

**例:**

## 爪哇

```java
// Java Program to show working of Enum 
// Keyword when declared outside the Class
enum Days {
    MONDAY,
    TUESDAY,
    WEDNESDAY,
    THURSDAY,
    FRIDAY,
    SATURDAY,
    SUNDAY;
}

public class temp {

    // Driver method
    public static void main(String[] args)
    {
        Days x = Days.FRIDAY;
        System.out.println(x);
    }
}
```

**输出:**

```java
FRIDAY

```

### **切换关键词**

[**Switch**](https://www.geeksforgeeks.org/switch-statement-in-java/) 语句在用户有**数量的选择**并且想要为每个选择执行不同的任务时很有帮助。Switch 语句允许根据值列表测试变量是否相等。每个值都称为一个案例。switch Case 语句通常与 **break 语句**一起使用，但它是可选的。

**例:**

## 爪哇

```java
// Java Program to show working
// of Switch statement
public class Example_Switch {

    public static void main(String[] args)
    {
        // Declare a variable for switch statement
        int num = 50;

        // Switch keyword
        switch (num) {
        // Case statements
        case 10:
            System.out.println("10");
            break;
        case 20:
            System.out.println("20");
            break;
        case 30:
            System.out.println("30");
            break;
        // Default case statement
        default:
            System.out.println("Other than 10, 20 or 30");
        }
    }
}
```

**输出:**

```java
Other than 10, 20 or 30

```

> 我们也可以在 Switch 语句中使用 Enum 关键字。我们可以像 int 原语一样在 Java 的 Switch case 语句中使用 Enum。下面是一些用开关语句来显示枚举工作的例子。

**示例 1:** 当枚举在主类

## 之外时，使用带 Switch 语句的枚举【Java】

```java
// Java Program to show the
// working of Enum keyword
// with Switch statement

// Enum keyword declared outside main class
enum Cars {
    BMW,
    JEEP,
    AUDI,
    VOLKSWAGON,
    NANO,
    FIAT;
}

// Main class
public class Main {
    public static void main(String args[])
    {
        // Declaring Enum variable
        Cars c;
        c = Cars.AUDI;
        // Switch keyword
        switch (c) {

        // Case statements
        case BMW:
            System.out.println("You choose BMW !");
            break;
        case JEEP:
            System.out.println("You choose JEEP !");
            break;
        case AUDI:
            System.out.println("You choose AUDI !");
            break;
        case VOLKSWAGON:
            System.out.println("You choose VOLKSWAGON !");
            break;
        case NANO:
            System.out.println("You choose NANO !");
            break;
        case FIAT:
            System.out.println("You choose FIAT !");

        default:
            System.out.println("NEW BRAND'S CAR.");
            break;
        }
    }
}
```

**输出:**

```java
You choose AUDI !

```

在上面的例子中，我们展示了当枚举在主类之外声明时，枚举关键字如何与 Switch case 语句一起工作。

**示例 2:** 当枚举在主类

## Java

```java
// Java Program to Show 
// working of Enum keyword
// with Switch statement

// Main class
public class MainClass {

    // Declaring Enum keyword
    // inside main class
    enum Webseries {
        GOT,
        Breakingbad,
        Lucifer,
        Boys,
        Mirzapur,
        Moneyheist;
    }
    public static void main(String[] args)
    {
        // Declaring and Assigning choice to variable 'wb'
        Webseries wb = Webseries.Mirzapur;

        // Switch Keyword

        switch (wb) {

        // Case statements
        case GOT:
            System.out.println("Game of Thrones selected");
            break;
        case Breakingbad:
            System.out.println("Breaking Bad selected");
            break;
        case Lucifer:
            System.out.println("Lucifer selected");
            break;
        case Boys:
            System.out.println("Boys selected");
            break;
        case Mirzapur:
            System.out.println("Mirzapur selected");
            break;
        case Moneyheist:
            System.out.println("Money Heist selected");
            break;
        default:
            System.out.println("You are outdated !!!");
            break;
        }
    }
}
```

内时，使用带有 Switch 语句的枚举

**输出:**

```java
Mirzapur selected

```

在上面的例子中，我们展示了当枚举在主类中声明时，枚举关键字如何与 Switch case 语句一起工作。