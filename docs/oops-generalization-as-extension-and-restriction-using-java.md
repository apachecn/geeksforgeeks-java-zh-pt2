# OOPS |使用 Java 作为扩展和限制的泛化

> 原文:[https://www . geesforgeks . org/oops-generalization-as-extension-and-restriction-use-Java/](https://www.geeksforgeeks.org/oops-generalization-as-extension-and-restriction-using-java/)

**一般化**是从两个或多个类中取出公共属性和功能，并将它们组合成另一个类的过程，该类充当这些类的父类，或者我们可以说这些专用类的一般化类。所有的子类都是一种超类。所以我们可以说子类“是-A”超类。因此，概括被称为“是-一种关系”
这里有一个概括的例子:

![generalization example](img/412ccdbb91788e5bb5f53ff1426966ff.png)

在这个图中，我们看到有两种类型的航班，所以我们制定了一个包含共同属性的航班等级，然后我们有一个国际和国内等级，这是航班等级的延伸，将有航班属性以及他们自己的属性。这里 flight 是父/超类，另外两个是子/子类。国际航班和国内航班一样都是“a”级航班。

**例 1:泛化为扩展**

```
// super or parent class
class Person 
{
    static int count = 1;
    String name;
    int age;
    String gender;
}

// subclass or child of Person
class Student extends Person 
{ 
    // name, age and gender 
    // get inherited from Person
    int rollNo;
    String course;
}

// subclass of Person
class Teacher extends Person 
{ 
    // name, age and gender 
    // get inherited from Person
    static int count = 20;
    String subject;
    int experience;
}

class Test {
    public static void main(String[] s)
    {
        Teacher t = new Teacher();
        t.name = "Shaan";

        // name gets inherited in teacher
        System.out.println(t.name); 

         // will give priority to its own count
        System.out.println(t.count);
    }
}
```

**Output:**

```
Shaan
20

```

**说明:**我们有两个班级老师和学生，他们有共同的属性，如姓名、年龄和性别，所以我们制作了另一个班级人，它有这些属性，然后从它扩展了这两个。现在，当我们创建一个教师类的对象时，我们就拥有了人类的所有属性。这里我们看到教师类有自己的 count 值，所以这将隐藏家长的值。我们没有在教师课堂上给出“名字”属性，但我们仍然在使用它。这是因为父类的所有属性和方法都继承到了子类中。我们在教师类中给出了仅属于教师类的附加属性。这些附加属性显示了泛化为子类提供的扩展。

**例 2:泛化为限制**

```
// abstract super class
abstract class User
{
    String name;
    int age;
    String occupation;

    // abstract method
    abstract void fillForm(String name, String occupation); 
}

// non abstract sub class of User
class Doctor extends User 
{
    String specialization;

    // extra attributes
    int experience; 

    // doesn't give implementation of fillForm() method
}
class Test {
    public static void main(String[] s)
    {
        User u = new User();

        // extra attribute of child class so will
        // not be accessible to parent class
        u.experience = 10; 

    }
}
```

**输出:** 3 个错误–

1.  医生不是抽象的，不会覆盖用户

    ```
    class Doctor extends User
                   ^
    ```

    中的抽象方法 fillForm(字符串，String)
2.  用户是抽象的；无法实例化

    ```
      User u = new User();
                      ^
    ```

3.  cannot find symbol

    ```
     u.experience = 10;
                         ^
    ```

    **符号:**可变体验
    **位置:**用户类型的可变 u

**说明:** User 是一个抽象类，它有一个抽象 methodfillForm()，因为对于一个病人和医生来说表单会有所不同，所以填写表单也会有所不同。现在博士班要么必须提供自己的身体，要么必须声明自己是抽象的。这是超类对子类的限制，即子类必须继承其所有属性和功能，并且不能跳过任何属性和功能。它们可以通过覆盖现有特性来提供另一种实现，但不能跳过它。在这种情况下，这将生成编译错误，因为医生既不是抽象的，也没有为 fillform()方法提供主体。另一个原因是用户类没有体验属性，它只在医生类中，所以用户不能访问它。

**在上面的例子**中，我们看到一个子类必须从它的父类继承所有的特性，尽管它可以通过覆盖它来改变它的实现，但是它不能忽略父类的任何特性。这说明了概括的限制性形式。
我们还看到子类有自己的属性，父类对象不能使用，因为这些扩展属性只属于子类。这种额外属性的添加显示了
一种可扩展的概括形式。