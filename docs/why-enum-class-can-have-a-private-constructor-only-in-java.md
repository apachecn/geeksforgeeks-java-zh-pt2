# 为什么枚举类只能在 Java 中有私有构造函数？

> 原文:[https://www . geesforgeks . org/why-enum-class-can-have-a-private-constructor-only-in-Java/](https://www.geeksforgeeks.org/why-enum-class-can-have-a-private-constructor-only-in-java/)

每个枚举常数都是静态的。如果我们想表示一个名为常量的组，那么我们应该选择枚举。因此，我们可以通过使用枚举名称来访问它。

**没有构造函数的枚举:**

```java
enum Day{
 SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY;
}
```

**带构造函数的枚举:**

```java
enum Size {
 SMALL("The size is small."),
 MEDIUM("The size is medium."),
 LARGE("The size is large."),
 EXTRALARGE("The size is extra large.");

 private final String pizzaSize;
 // private enum constructor
 private Size(String pizzaSize) {
    this.pizzaSize = pizzaSize;
 }

 public String getSize() {
    return pizzaSize;
 }
}
```

**为什么不能有一个公共的枚举构造函数？**

我们需要枚举构造函数是私有的，因为枚举定义了一组有限的值(小、中、大)。如果建造者是公众，人们可能会创造更多的价值。(例如，无效/未声明的值，如 ANYSIZE、YOURSIZE 等。).

Java 中的枚举包含固定的常量值。因此，没有理由使用公共或受保护的构造函数，因为您无法创建枚举实例。此外，请注意，内部枚举被转换为类。由于我们不能显式创建枚举对象，因此我们不能直接调用枚举构造函数。

## 爪哇

```java
enum PizzaSize {

   // enum constants calling the enum constructors 
   SMALL("The size is small."),
   MEDIUM("The size is medium."),
   LARGE("The size is large."),
   EXTRALARGE("The size is extra large.");

   private final String pizzaSize;

   // private enum constructor
   private PizzaSize(String pizzaSize) {
      this.pizzaSize = pizzaSize;
   }

   public String getSize() {
      return pizzaSize;
   }
}

class GFG {
   public static void main(String[] args) {
      PizzaSize size = PizzaSize.SMALL;
      System.out.println(size.getSize());
   }
}
```

**输出**

```java
The size is small.

```