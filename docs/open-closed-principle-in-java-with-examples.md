# Java 中的开闭原理举例

> 原文:[https://www . geesforgeks . org/open-closed-principle-in-Java-with-examples/](https://www.geeksforgeeks.org/open-closed-principle-in-java-with-examples/)

在软件开发中，使用面向对象的设计是至关重要的。它有助于编写灵活、可扩展和可重用的代码。建议开发者在编写代码时遵循 [SOLID 原则](https://www.geeksforgeeks.org/solid-principle-in-programming-understand-with-real-life-examples/)。五个固体原则之一是开放/封闭原则。该原则声明软件实体像类、模块、函数等。；应该能够在不修改类行为的情况下扩展它。该原则将现有代码与修改模式分开，以提供更好的稳定性、可维护性，并最大限度地减少代码中的更改。简而言之，每次需求改变时，开发人员必须只需要改变代码的特定部分(一个类或一个函数)。

使用静态类型的语言，如 Java、C#等。开放/封闭原则通常通过使用继承和多态性来实现。让我们用几个例子来理解它。

**实施:**

计算体积的程序，让我们考虑构建一个计算所有几何对象体积的应用程序的任务。

*   长方体类存储长方体的尺寸
*   稍后，应用程序类将计算几何对象的总体积，这些对象目前只是长方体。
*   Run 类有助于运行整个程序。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate Open Closed Principle

// Class 1
// Helper class
// To store dimensions of a cuboid
// length, breadth and height
class Cuboid {

    // Member variables
    public double length;
    public double breadth;
    public double height;
}

// Class 2
// Helper class
// To calculate the volume of geometric objects
class Application {

    // It returns the total volume of the geometric objects
    public double get_total_volume(Cuboid[] geo_objects)
    {
        // Variable to store total volume
        double vol_sum = 0;

        // Iteratively calculating the volume of each object
        // and adding it to the total volume
        for (Cuboid geo_obj : geo_objects) {

            // Iteratively calculating the volume of each object
            // and adding it to the total volume
            vol_sum += geo_obj.length * geo_obj.breadth
                       * geo_obj.height;
        }

        // returning the to total volume
        return vol_sum;
    }
}

// Class 3
// Main Class
// To demonstrate working of all classes
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Initializing a cuboid one & declaring dimensions by
        // creating an object of Cuboid class in main() method
        Cuboid cb1 = new Cuboid();

        // Custom entries
        cb1.length = 5;
        cb1.breadth = 10;
        cb1.height = 15;

        // Similarly, initializing a cuboid2 and declaring dimensions
        // by creating object of Cuboid class in the man() method
        Cuboid cb2 = new Cuboid();

        // Custom entries
        cb2.length = 2;
        cb2.breadth = 4;
        cb2.height = 6;

        // Initializing a cuboid3 and declaring dimensions by
        // creating object of Cuboid class in the main() method
        Cuboid cb3 = new Cuboid();

        // Custom entries
        cb3.length = 3;
        cb3.breadth = 12;
        cb3.height = 15;

        // Now, declaring andinitializing Array of cuboids
        Cuboid[] c_arr = new Cuboid[3];
        c_arr[0] = cb1;
        c_arr[1] = cb2;
        c_arr[2] = cb3;

        // Initializing the Application class
        Application app = new Application();

        // Getting the total volume
        // using get_total_volume
        double vol = app.get_total_volume(c_arr);

        // Print and Display the Total Volume
        System.out.println("The total volume is " + vol);
    }
}
```

**Output**

```java
The total volume is 1338.0
```

> 现在，假设客户也希望应用程序计算球体的体积。为了适应新类型的几何对象，应用程序也需要更改。

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate Open Closed Principle

// class 1
// Helper class
// To store dimensions of a cuboid
// used to store length, breadth and height of a cuboid
class Cuboid {

    // Member variables of this class
    public double length;
    public double breadth;
    public double height;
}

// Class 2
// Helper class
// To store dimensions of a sphere
class Sphere {

    // Storing radius of a sphere
    public double radius;
}

// Class 3
// Helper class
// This class helps to calculate the volume of geometric
// objects
class Application {

    // Returning the total volume of the geometric objects
    public double get_total_volume(Cuboid[] c_geo_objects,
                                   Sphere[] s_geo_objects)
    {
        // Variable used to store total volume
        double vol_sum = 0;

        // Iteratively calculating the volume of each Cuboid
        // and adding it to the total volume

        // Iterating using for each loop to
        // calculate the volume of a cuboid
        for (Cuboid geo_obj : c_geo_objects) {

            vol_sum += geo_obj.length * geo_obj.breadth
                       * geo_obj.height;
        }

        // Iterating using for each loop to
        // calculate the volume of a cuboid
        for (Sphere geo_obj : s_geo_objects) {

            // Iteratively calculating the volume of each
            // Sphere and adding it to the total volume
            vol_sum += (4 / 3) * Math.PI * geo_obj.radius
                       * geo_obj.radius * geo_obj.radius;
        }

        // Returning the to total volume
        return vol_sum;
    }
}

// Class 4
// Main class
// To demonstrate working of all classes
public class GFG {

    //  Main driver method
    public static void main(String args[])
    {
        // Initializing a cuboid one as well as declaring
        // its dimensions.
        Cuboid cb1 = new Cuboid();
        cb1.length = 5;
        cb1.breadth = 10;
        cb1.height = 15;

        // Initializing a cuboid two as well as declaring
        // its dimensions.
        Cuboid cb2 = new Cuboid();
        cb2.length = 2;
        cb2.breadth = 4;
        cb2.height = 6;

        ////Initializing a cuboid three as well as declaring
        /// its dimensions.
        Cuboid cb3 = new Cuboid();
        cb3.length = 3;
        cb3.breadth = 12;
        cb3.height = 15;

        // Initializing and declaring an array of cuboids
        Cuboid[] c_arr = new Cuboid[3];
        c_arr[0] = cb1;
        c_arr[1] = cb2;
        c_arr[2] = cb3;

        // Initializing a sphere one as well as declaring
        // its dimension.
        Sphere sp1 = new Sphere();
        sp1.radius = 5;

        // Initializing a sphere two as well as declaring
        // its dimension.
        Sphere sp2 = new Sphere();
        sp2.radius = 2;

        // Initializing a sphere three as well as declaring
        // its dimension.
        Sphere sp3 = new Sphere();
        sp3.radius = 3;

        // Initializing and declaring an array of spheres
        Sphere[] s_arr = new Sphere[3];
        s_arr[0] = sp1;
        s_arr[1] = sp2;
        s_arr[2] = sp3;

        // Initializing Application class
        Application app = new Application();

        // Getting the total volume
        // using get_total_volume
        double vol = app.get_total_volume(c_arr, s_arr);

        // Print and display the total volume
        System.out.println("The total volume is " + vol);
    }
}
```

**Output**

```java
The total volume is 1840.6548245743668
```

**输出说明:**

正如我们所看到的，应用程序类必须被改变以适应球体。代码中的任何更改都可能导致未来出现一些意外错误——因此，每次需求发生变化时都更改经过良好测试的代码是不明智的。让我们尝试应用 Open Close 原则，看看是否可以在不对应用程序类进行任何更改的情况下添加一个球体(一种新类型的对象)。

**解决方案:**

*   创建一个抽象类，作为所有类型对象的基类。
*   所有几何对象都有一组尺寸和一个 get_volume 方法(两者对于每种类型的对象都是不同的)。
*   对于每种类型的对象(本例中为几何对象)，继承“Geo_object”类，添加该类型对象的尺寸，并覆盖“ *get_volume* ”方法。
*   很明显，通过将体积计算从“应用”类转移到不同的类，添加新类型的几何对象将不需要改变“应用”类。

**例 3:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate Open Closed Principle

// Importing all classes from java.math package
// to compute mathematic calculations
import java.math.*;

// Class 1
// Helper Class
// Abstract class--which needs to be extended
abstract class Geo_objects {

   // Abstract function--which needs to overriden
    public abstract double get_volume();
}

// Class 2
// Helper Class
// Extending the Geo_objects to fit cuboid dimensions
class Cuboid_2 extends Geo_objects {

    // used to store length, breadth and height of a cuboid

    public double length;
    public double breadth;
    public double height;

    // overrided function to calculate
    // the volume of a cuboid
    // @Override
    public double get_volume()
    {
        return length * breadth * height;
    }
}

// Class 3
// Helper Class
// Extending Geo_objects to fit sphere dimension
 class Sphere_2 extends Geo_objects {

    // To store radius of a sphere
    public double radius;

    // Overrided function to calculate
    //  the volume of a sphere

    //@Override
    public double get_volume()
    {
        return (4 / 3) * Math.PI * radius * radius * radius;
    }
}

// Class 4
// Helper class
// To calculate the volume of geometric objects
class Application {

    public double
        get_total_volume(Geo_objects[] geo_objects)
    {
        // Initially initializing sum to zero
        double vol_sum = 0;

        // Iterating using for each loop
        for (Geo_objects geo_obj : geo_objects) {
            vol_sum += geo_obj.get_volume();
        }

        return vol_sum;
    }
}

// Class 5
// Main class
// To demonstrate working of all classes
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Initializing cuboid1 as well as declaring
        // its dimensions.
        Cuboid_2 cb1 = new Cuboid_2();

        // Custom entries
        cb1.length = 5;
        cb1.breadth = 10;
        cb1.height = 15;

        // Initializing Cuboid2 as well as declaring
        // its dimensions.
        Cuboid_2 cb2 = new Cuboid_2();
        cb2.length = 2;
        cb2.breadth = 4;
        cb2.height = 6;

        // initializing Cuboid3 as well as declaring
        // its dimensions.
        Cuboid_2 cb3 = new Cuboid_2();
        cb3.length = 3;
        cb3.breadth = 12;
        cb3.height = 15;

        // initializing Sphere1 as well as declaring
        // its dimension.
        Sphere_2 sp1 = new Sphere_2();
        sp1.radius = 5;

        // initializing Sphere2 as well as declaring
        // its dimension.
        Sphere_2 sp2 = new Sphere_2();
        sp2.radius = 2;

        // initializing Sphere3 as well as declaring
        // its dimension.
        Sphere_2 sp3 = new Sphere_2();
        sp3.radius = 3;

        // Now, initializing and declaring
        // an array of Geo_objects
        Geo_objects[] g_arr = new Geo_objects[6];

        // Setting Geo_objects to cuboid class
        g_arr[0] = cb1;
        g_arr[1] = cb2;
        g_arr[2] = cb3;

        // Setting Geo_objects to sphere class
        g_arr[3] = sp1;
        g_arr[4] = sp2;
        g_arr[5] = sp3;

        // Initializing the Application class
        Application app = new Application();

        // Getting the total volume
        // using get_total_volume
        double vol = app.get_total_volume(g_arr);

        // Printing total volume
        System.out.println("The total volume is " + vol);
    }
}
```

**Output**

```java
The total volume is 1840.6548245743668
```

**输出说明:**

应用程序类因修改而关闭。请注意，可能还有其他方法来实现开放关闭原则——我们的方法只是可能的方法之一。

> 在进行概述时，我们发现我们的第一种方法没有开放扩展，需要在代码中进行修改以适应新的需求(新的几何对象)。虽然第二种方法对扩展开放，但是添加新的需求可以在不修改任何现有代码的情况下完成。第二种方法有助于实现整个程序的健壮性。