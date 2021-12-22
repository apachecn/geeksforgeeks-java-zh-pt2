# 在 Java 中使用带继承的 final】

> 原文:[https://www . geesforgeks . org/using-final-with-inheritation-in-Java/](https://www.geeksforgeeks.org/using-final-with-inheritance-in-java/)

先决条件–[在 java 中重写](https://www.geeksforgeeks.org/overriding-in-java/)、[继承](https://www.geeksforgeeks.org/inheritance-in-java/)
[**最终**](https://www.geeksforgeeks.org/g-fact-48/) 是 java 中用于限制某些功能的关键字。我们可以用 final 关键字声明变量、方法和类。

**使用最终带继承**

在继承过程中，我们必须用 final 关键字声明方法，对于这些方法，我们需要在所有派生类中遵循相同的实现。请注意，没有必要在继承的初始阶段声明最终方法(始终是基类)。我们可以在我们想要的任何子类中声明最终方法，如果任何其他类扩展了这个子类，那么它必须遵循该子类中相同的方法实现。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// use of final with inheritance

// base class
abstract class Shape
{
    private double width;

    private double height;

    // Shape class parameterized constructor
    public Shape(double width, double height)
    {
        this.width = width;
        this.height = height;
    }

    // getWidth method is declared as final
    // so any class extending
    // Shape can't override it
    public final double getWidth()
    {
        return width;
    }

    // getHeight method is declared as final
    // so any class extending Shape
    // can not override it
    public final double getHeight()
    {
        return height;
    }

    // method getArea() declared abstract because
    // it upon its subclasses to provide
    // complete implementation
    abstract double getArea();
}

// derived class one
class Rectangle extends Shape
{
    // Rectangle class parameterized constructor
    public Rectangle(double width, double height)
    {
        // calling Shape class constructor
        super(width, height);
    }

    // getArea method is overridden and declared
    // as final    so any class extending
    // Rectangle can't override it
    @Override
    final double getArea()
    {
        return this.getHeight() * this.getWidth();
    }

}

//derived class two
class Square extends Shape
{
    // Square class parameterized constructor
    public Square(double side)
    {
        // calling Shape class constructor
        super(side, side);
    }

    // getArea method is overridden and declared as
    // final so any class extending
    // Square can't override it
    @Override
    final double getArea()
    {
        return this.getHeight() * this.getWidth();
    }

}

// Driver class
public class Test
{
    public static void main(String[] args)
    {
        // creating Rectangle object
        Shape s1 = new Rectangle(10, 20);

        // creating Square object
        Shape s2 = new Square(10);

        // getting width and height of s1
        System.out.println("width of s1 : "+ s1.getWidth());
        System.out.println("height of s1 : "+ s1.getHeight());

        // getting width and height of s2
        System.out.println("width of s2 : "+ s2.getWidth());
        System.out.println("height of s2 : "+ s2.getHeight());

        //getting area of s1
        System.out.println("area of s1 : "+ s1.getArea());

        //getting area of s2
        System.out.println("area of s2 : "+ s2.getArea());

    }
}
```

输出:

```
width of s1 : 10.0
height of s1 : 20.0
width of s2 : 10.0
height of s2 : 10.0
area of s1 : 200.0
area of s2 : 100.0
```

**使用 final 防止继承**

当一个类被声明为最终类时，它不能被子类化，也就是说，没有任何其他类可以扩展它。例如，当[创建像预定义的](https://www.geeksforgeeks.org/create-immutable-class-java/)[字符串](https://www.geeksforgeeks.org/string-class-in-java/)类那样的不可变类时，这特别有用。下面的片段用一个类来说明**最终的**关键词:

```
final class A
{
     // methods and fields
}
// The following class is illegal.
class B extends A 
{ 
    // ERROR! Can't subclass A
}
```

**注:**

*   将类声明为 final 也会隐式地将其所有方法声明为 final。
*   将一个类声明为**抽象**和**最终**是非法的，因为抽象类本身是不完整的，并且依赖它的子类来提供完整的实现。有关抽象类的更多信息，请参考 java 中的[抽象类](https://www.geeksforgeeks.org/abstract-classes-in-java/)

**使用 final 防止覆盖**

当一个方法被声明为 final 时，它不能被子类覆盖。[对象](https://www.geeksforgeeks.org/object-class-in-java/)类做到了这一点——它的许多方法都是最终的。下面的片段用一个方法来说明**最终的**关键词:

```
class A 
{
    final void m1() 
    {
        System.out.println("This is a final method.");
    }
}

class B extends A 
{
    void m1()
    { 
        // ERROR! Can't override.
        System.out.println("Illegal!");
    }
}
```

通常，Java 会在运行时动态解析对方法的调用。这叫 [**后期或动态绑定**](https://www.geeksforgeeks.org/dynamic-method-dispatch-runtime-polymorphism-java/) 。但是，由于最终方法不能被重写，因此对最终方法的调用可以在编译时解析。这叫 [**早或静绑定**](https://www.geeksforgeeks.org/static-vs-dynamic-binding-in-java/) 。
本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。