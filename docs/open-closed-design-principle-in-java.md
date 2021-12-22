# Java 中的开放封闭设计原理

> 原文:[https://www . geesforgeks . org/open-closed-design-principle-in-Java/](https://www.geeksforgeeks.org/open-closed-design-principle-in-java/)

开放封闭设计原则是软件开发领域最重要的设计原则之一。这是一组 5 个设计原则的一部分，通常被称为首字母缩略词“固体”

```
S - Single Responsibility Principle
O - Open Closed Principle
L - Liskov Substitution Principle
I - Interface Segregation
D - Dependency Inversion
```

根据罗伯特·马丁的观点，这个原则规定软件实体(类、模块、函数)应该对扩展开放，对修改关闭。这意味着一个类应该足够灵活，以适应业务需求变化时的变化，而不会破坏现有的代码。因此，从属类不必改变。这最大限度地减少了测试工作，我们只需要关注新的代码更改。

**方法:**

基本上有两种实现接口的主要方式:

1.  使用[继承](https://www.geeksforgeeks.org/inheritance-in-java/)
2.  使用[接口](https://www.geeksforgeeks.org/interfaces-in-java/)和[抽象方法](https://www.geeksforgeeks.org/abstract-methods-in-java-with-examples/)

**方法 1:** 利用遗传

遵循这个原则的一个方法是使用继承。我们有一个超类，它被关闭进行修改，并且是基线的，是 jar 文件的一部分。任何想要修改超类行为的人都可以对其进行子类化、扩展和添加新特性。这确保了超类行为保持不变，并且超类的客户端不必进行代码更改。然而**、**继承引入了超类和子**–**类实现之间的紧密耦合。假设超类有缺陷或者超类版本有升级引入了代码变更，那么子类也需要修改。

**例子:**假设简开了一家面包店，并决定根据她的销售额保持简单和规模。

## Java

```
// Java Program to Illustrate Open Closed Design Principle
// Using Inheritance

// Importing input output classes
import java.io.*;

// Class 1
// Helper class acting as parent class
class Cake {

    // Member variable of Cake class
    private int size;
    private float weight;

    // Constructor for cake which sets
    // only size and dimension of cake
    public Cake(int size, float weight)
    {
        // This keyword refers to current object itself
        this.size = size;
        this.weight = weight;
    }

    // Method
    // To bake the cake
    public void bake()
    {
        // Display message only
        System.out.println(
            "Baking cake with base as vanilla");

        // Print and display the size and weight of the cake
        System.out.println("Size is " + this.size
                           + " inches and weight is "
                           + this.weight + " kg.");
    }
}

// Class 2
// Helper class(Child class) of class 1
class PineappleCake extends Cake {

    // Member variables
    private int size;
    private float weight;

    // Constructor
    // To set the dimension of the pineapple cake
    public PineappleCake(int size, float weight)
    {
        // Super keyword refers to parent class instance
        super(size, weight);

        // This keyword refer to current instance
        this.size = size;
        this.weight = weight;
    }

    // Method 1
    // To decorate the pineapple cake
    private void decorateCake()
    {
        // Display messages only
        System.out.println("Decorating cake");
        System.out.println("Adding pineapple pieces");
    }

    // Method 2
    // To add cream to pineapple cake
    private void addCream()
    {
        // Print statement
        System.out.println("Adding white cream");
    }

    // Method 3
    // To bake a pineapple cake
    public void bake()
    {

        super.bake();

        // Calling the above two methods created
        addCream();
        decorateCake();

        // Print the dimension of the pineapple cake
        System.out.println("Pineapple cake - " + this.size
                           + " inches is ready");
    }
}

// Class 3
// Helper class(Child class) of class 1
class ChocolateCake extends Cake {

    // member variables
    private int size;
    private float weight;

    // Constructor
    // Setting the size nd weight of the chocolate cake
    public ChocolateCake(int size, float weight)
    {

        super(size, weight);

        this.size = size;
        this.weight = weight;
    }

    // Method 1
    // To decorate a chocolate cake
    private void decorateCake()
    {

        // Display commands only
        System.out.println("Decorating cake");
        System.out.println("Adding chocolate chips");
    }

    // Method 2
    // To add cream to chocolate cake
    private void addCream()
    {

        // Print statement
        System.out.println("Adding chocolate cream");
    }

    // Method 3
    // to bake a chocolate cake
    public void bake()
    {

        super.bake();

        // Calling the above two methods created
        addCream();
        decorateCake();

        // Print and display the dimension of chocolate cake
        System.out.println("Chocolate cake - " + this.size
                           + " inches is ready");
    }
}

// Class 4
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an instance of pineapple cake
        // int the main() method

        // Custom dimension are passed as in arguments
        PineappleCake pineappleCake
            = new PineappleCake(7, 3);

        // Calling the bake() method of PineappleCake class
        // to bake the cake
        pineappleCake.bake();

        // Similarly, creating an instance of chocolate cake
        // in the main() method
        ChocolateCake chocolateCake
            = new ChocolateCake(5, 2);

        // Calling the bake() method of ChocolateCake class
        // to bake the cake
        chocolateCake.bake();
    }
}
```

**输出**

```
Baking cake with base as vanilla
Size is 7 inches and weight is 3.0 kg.
Adding white cream
Decorating cake
Adding pineapple pieces
Pineapple cake - 7 inches is ready
Baking cake with base as vanilla
Size is 5 inches and weight is 2.0 kg.
Adding chocolate cream
Decorating cake
Adding chocolate chips
Chocolate cake - 5 inches is ready
```

**输出说明:**‘饼’类为基类。每个蛋糕的底部都有香草的味道。我们有两种特色菜，即菠萝和巧克力风味蛋糕。这些类使用 Cake 的 bake()方法制作香草蛋糕，然后添加奶油并根据口味装饰蛋糕。

> **注:**之后几天，简氏面包店销量都很高。所以她决定烘焙不同口味的蛋糕，为顾客提供更多的品种。有了这些新的需求，我们需要改变‘Cake’类的构造函数，这样做上面代码中的变化就会体现出来。代码更改如下。然而，我们需要修改子类来接受第三个参数——代码工作的风格。

**例:**

## 爪哇

```
// Java Program to Illustrate Open Closed Design Principle
// Using Inheritance
// Alonside adding Parameter - Flavor to cakes

// Importing input output classes
import java.io.*;

// Class 1
// Helper class
// Acting as parent class
class Cake {

    // Member variables
    private int size;
    private float weight;

    // This is new declared variable to
    // hold the flavour for the cake
    private String flavor;

    // Constructor
    // To set the dimensions for the cake
    public Cake(int size, float weight, String flavor)
    {

        this.size = size;
        this.weight = weight;

        // Here this keyword sets the
        // current instance flavour to th cake
        this.flavor = flavor;
    }

    // Method
    // To bake the cake
    public void bake()
    {

        // Printing the flavour of the desired cake
        System.out.println("Baking cake with base as "
                           + this.flavor);

        // Printing the size and weight of the same cake
        System.out.println("Size is " + this.size
                           + " inches and weight is "
                           + this.weight + " kg.");
    }
}

// Class 2
// Helper class
class PineappleCake extends Cake {

    // Member variables for the pineapple cake
    private int size;
    private float weight;
    private String flavor;

    // Constructor
    // Updated as per requirements as sales rise flavour is
    // added, so do setting  the flavour
    public PineappleCake(int size, float weight,
                         String flavor)
    {

        // Super keyword refers to parent class
        super(size, weight, flavor);

        // This keyword refers to current instance
        this.size = size;
        this.weight = weight;
        this.flavor = flavor;
    }

    // Method 1
    // To decorate the cake
    private void decorateCake()
    {

        // Display commands only
        System.out.println("Decorating cake");
        System.out.println("Adding pineapple pieces");
    }

    // Method 2
    // To add cream to the flavored pineapple cake
    private void addCream()
    {

        System.out.println("Adding white cream");
    }
    // Method 3
    // To bake a flavored pineapple cake
    public void bake()
    {

        // Super keyword calls the Cake class bake() method
        super.bake();

        // Calling the above two methods
        addCream();
        decorateCake();

        // Printing the dimensions of
        // flavoured pineapple cake
        System.out.println("Pineapple cake - " + this.size
                           + " inches is ready");
    }
}

// Similarly setting the same for
// the 'flavoured' chocolate cake

// Class 3
// Helper class (Base class of parent class)
class ChocolateCake extends Cake {

    private int size;
    private float weight;
    private String flavor;

    // Updated constructor
    public ChocolateCake(int size, float weight,
                         String flavor)
    {

        super(size, weight, flavor);

        this.size = size;
        this.weight = weight;
        this.flavor = flavor;
    }

    // Method 1
    // To decorate the flavored chocolate cake
    private void decorateCake()
    {

        System.out.println("Decorating cake");
        System.out.println("Adding chocolate chips");
    }

    // Method 2
    // To add cream to the flavoured chocolate cake
    private void addCream()
    {

        System.out.println("Adding chocolate cream");
    }

    // Method 3
    // To bake a flavoured chocolate cake
    public void bake()
    {

        super.bake();

        addCream();
        decorateCake();

        System.out.println("Chocolate cake - " + this.size
                           + " inches is ready");
    }
}

// Class 4
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a pineapple cake in the main() method
        // Custom dimensions are passed as in arguments
        PineappleCake pineappleCake
            = new PineappleCake(7, 3, "vanilla");

        // Calling the bake() method of the PineappleCake
        // Class to bake the pinelapple cake
        pineappleCake.bake();

        // Similarly repeating the same with the chocolate
        // cake

        // Creating a chocolate cake by creating an object
        // of ChocolateCake class in the main method
        ChocolateCake chocolateCake
            = new ChocolateCake(5, 2, "chocolate");

        // Calling the bake() method of the ChocolateCake
        // Class to bake the chocolate cake
        chocolateCake.bake();
    }
}
```

**输出**

```
Baking cake with base as vanilla
Size is 7 inches and weight is 3.0 kg.
Adding white cream
Decorating cake
Adding pineapple pieces
Pineapple cake - 7 inches is ready
Baking cake with base as chocolate
Size is 5 inches and weight is 2.0 kg.
Adding chocolate cream
Decorating cake
Adding chocolate chips
Chocolate cake - 5 inches is ready
```