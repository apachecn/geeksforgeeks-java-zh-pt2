# Java 程序输出|自动装箱和拆箱

> 原文:[https://www . geesforgeks . org/output-of-Java-programs-auto boxing-and-unboxing/](https://www.geeksforgeeks.org/output-of-java-programs-autoboxing-and-unboxing/)

先决条件–[在 Java 中自动装箱和拆箱](https://www.geeksforgeeks.org/autoboxing-unboxing-java/)

**1)以下程序的输出是什么？**

```java
class Main {
    public static void main(String[] args)
    {
        Double x1, y1, z1;
        double x2, y2, z2;
        x1 = 10.0;
        y1 = 4.0;
        z1 = x1 * x1 + y1 * y1;
        x2 = 10.0;
        y2 = 4.0;
        z2 = x2 * x2 + y2 * y2;
        System.out.print(z1 + " ");
        System.out.println(z2);
    }
}
```

**选项:**T2 a . 116.0 116.0
b .运行时错误
C .编译时错误
D. 116 116.0

**回答:** A. 116.0 116.0

**说明:**首先，数值 10.0 和 20.0 分别在 x1 和 y1 中自动装箱。然后为了计算 z1，x1 和 y1 被取消装箱，表达式被求值，然后结果被装箱为 z1。打印 z1 时，它会自动取消装箱，打印值后再重新装箱。z2 通常使用原始数据类型计算。

**2)以下程序的输出是什么？**

```java
class Main {
    public static void main(String[] args)
    {
        Boolean b1 = true;
        Boolean b2 = false;
        System.out.print((b1 == b2) + " ");
        System.out.print(b1.equals(b2));
    }
}
```

**选项:**
A .编译时错误
B .假假
C .假真
D .真真

**回答:** B .假假

**说明:**真值和假值分别在 b1 和 b2 中自动装箱。对于 b1==b2，b1 和 b2 取消装箱，然后进行比较，返回 false。对于 b1.equals(b2)，由于 b1 和 b2 是布尔对象，因此可以使用 equals()方法对它们进行比较。这也会返回 false，因为 b1 和 b2 不相等。

**3)以下程序的输出是什么？**

```java
class Main {
    public static void main(String args[])
    {
        Double x = new Double(10);
        double i = x.doubleValue();
        System.out.print(i + " " + x);
    }
}
```

**选项:**T2 a .编译时错误
b . 10 10
c . 10.0 10.0
d . 10 10.0

**回答:** C. 10.0 10.0

**说明:** x 是 Double 类型的对象。因此，当打印 x 时，它将自动取消装箱，并打印 10.0。然而，doubleValue()是一种将 double 对象取消装箱为 Double 的方法。因此，我的值也是 10.0。

**4)以下程序的输出是什么？**

```java
class Main {
    static int funct(Integer x)
    {
        return x;
    }
    public static void main(String args[])
    {
        Integer x = funct(10);
        System.out.println(x);
    }
}
```

**选项:**
A .编译时错误
B .运行时错误
C. 10
D .无输出

**答案:** C. 10

**说明:**当 10 传入 funct()时，自动装箱。当该值从 funct 返回时，它被自动装箱，然后该值在 x 中再次被自动装箱。当 x 被打印时，它再次被取消装箱。

**5)以下程序的输出是什么？**

```java
class Main {
    public static void main(String args[])
    {
        Boolean b1 = "TRUE";
        Boolean b2 = "FALSE";
        boolean b = b1 && b2;
        System.out.println(b);
    }
}
```

**选项:**T2 a .编译时错误
B .假
C .假
D .真

**答案:** A .编译时错误

**解释:**这将是一个编译时错误，因为“真”和“假”是字符串，不能转换为布尔值。