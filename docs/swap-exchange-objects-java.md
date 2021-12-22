# 如何在 Java 中交换或交换对象？

> 原文:[https://www.geeksforgeeks.org/swap-exchange-objects-java/](https://www.geeksforgeeks.org/swap-exchange-objects-java/)

为了理解如何在 Java 中交换对象，让我们考虑下面的一个插图，如下所示****:****

**插图:**

> **假设我们有一个名为“Car”的类，带有一些属性。我们创建 Car 的两个对象，比如 car1 和 car2，car1 和 car2 的数据如何交换？**

****方法:****

1.  **使用 OOPS 的概念**
2.  **使用 java 的包装类**

****方法 1:** 使用 OOPS 的概念**

**在这里，我们将简单地交换成员，让我们直接拿一个样本“汽车”插图来玩。所以如果类‘Car’只有一个整数属性说“no”(车号)，我们可以通过简单地交换两辆车的成员来交换汽车。**

****实施例 1-A****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to demonstrate that we can swap two
// objects be swapping members

// Class 1
// Number class Car
class Car {
    // Attributes associated with car
    int no;
    Car(int no) { this.no = no; }
}

// Class 2
// Uses Car objects
class GFG {
    // Method 1
    // To swap
    public static void swap(Car c1, Car c2)
    {
        int temp = c1.no;
        c1.no = c2.no;
        c2.no = temp;
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Creating car class objects(creating cars)
        Car c1 = new Car(1);
        Car c2 = new Car(2);

        // Calling method 1
        swap(c1, c2);

        // Print and display commands
        System.out.println("c1.no = " + c1.no);
        System.out.println("c2.no = " + c2.no);
    }
}
```

****Output**

```
c1.no = 2
c2.no = 1
```** 

> ****注:**极客，如果我们不认识 Car 的成员怎么办？**
> 
> **上面的解决方案是有效的，因为我们知道 Car 中有一个成员“否”。如果我们不知道 Car 的成员或者成员名单太大怎么办。T *his 是一种非常常见的情况，因为使用其他类的类可能无法访问其他类的成员*。下面的解决方案有效吗？**

****例 1-B****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to demonstrate that we can swap two
// objects be swapping members
// Where it does not work

// Class 1
// A car with number and name
class Car {

    // Attributes of Car class
    int model, no;

    // Constructor
    Car(int model, int no)
    {
      // This keyword is used to refer
      // current instance itself
        this.model = model;
        this.no = no;
    }

    // Method of this class
    // To print Car
    void print()
    {
       // Printing number and model of car
        System.out.println("no = " + no +
                           ", model = " + model);
    }
}

// Class 2
// A class that uses Car
class Main
{
    // swap() doesn't swap c1 and c2
    public static void swap(Car c1, Car c2)
    {
        Car temp = c1;
        c1 = c2;
        c2 = temp;
    }

    // Driver method
    public static void main(String[] args)
    {
        Car c1 = new Car(101, 1);
        Car c2 = new Car(202, 2);
        swap(c1, c2);
        c1.print();
        c2.print();
    }
}
```

****Output**

```
no = 1, model = 101
no = 2, model = 202
```** 

****输出说明:**从上面的输出中我们可以看到，对象没有被交换。我们在[之前的帖子](https://www.geeksforgeeks.org/g-fact-31-java-is-strictly-pass-by-value/)中讨论过，在 Java 中参数是通过值传递的。因此，当我们将 c1 和 c2 传递给 swap()时，函数 swap()会创建这些引用的副本。**

****方法 2:** [包装类](https://www.geeksforgeeks.org/wrapper-classes-java/)**

**如果我们创建一个包含 Car 引用的包装类，我们可以通过交换包装类的引用来交换 Car。**

****例****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to Demonstrate that Wrapper Classes
// Can be Used to Swap two Objects

// Class 1
// A car with model and no.
class Car {
    // Attributes associated with car
    int model, no;

    // Constructor of class 1
    Car(int model, int no)
    {
        // This refers to current instance itself
        this.model = model;
        this.no = no;
    }

    // Method
    // To print object details
    void print()
    {
        System.out.println("no = " + no
                           + ", model = " + model);
    }
}

// Class 2
// Wrapper over class that is used for swapping
class CarWrapper {
    Car c;

    // Constructor
    CarWrapper(Car c) { this.c = c; }
}

// Class 3
// Uses Car class and swaps objects of Car
// using CarWrapper
class GFG {
    // This method swaps car objects in wrappers
    // cw1 and cw2
    public static void swap(CarWrapper cw1, CarWrapper cw2)
    {
        Car temp = cw1.c;
        cw1.c = cw2.c;
        cw2.c = temp;
    }

    // Main driver method
    public static void main(String[] args)
    {
        Car c1 = new Car(101, 1);
        Car c2 = new Car(202, 2);
        CarWrapper cw1 = new CarWrapper(c1);
        CarWrapper cw2 = new CarWrapper(c2);
        swap(cw1, cw2);
        cw1.c.print();
        cw2.c.print();
    }
}
```

****输出:****

```
no = 2, model = 202
no = 1, model = 101
```

**因此，即使用户类无权访问其对象将被交换的类的成员，包装类解决方案也能工作。
本文由**阿努拉格·赖**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**