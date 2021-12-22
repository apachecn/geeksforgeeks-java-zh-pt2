# “这个”在 Java 中引用

> 原文:[https://www.geeksforgeeks.org/this-reference-in-java/](https://www.geeksforgeeks.org/this-reference-in-java/)

“this”是引用当前对象的引用变量。

以下是 java 中使用' this '关键字的方法:
**1。使用“this”关键字引用当前类实例变量**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
//Java code for using 'this' keyword to
//refer current class instance variables
class Test
{
    int a;
    int b;

    // Parameterized constructor
    Test(int a, int b)
    {
        this.a = a;
        this.b = b;
    }

    void display()
    {
        //Displaying value of variables a and b
        System.out.println("a = " + a + "  b = " + b);
    }

    public static void main(String[] args)
    {
        Test object = new Test(10, 20);
        object.display();
    }
}
```

输出:

```java
a = 10  b = 20
```

**2。使用此()调用当前类构造函数**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code for using this() to
// invoke current class constructor
class Test
{
    int a;
    int b;

    //Default constructor
    Test()
    { 
        this(10, 20);
        System.out.println("Inside  default constructor \n");
    }

    //Parameterized constructor
    Test(int a, int b)
    {
        this.a = a;
        this.b = b;
        System.out.println("Inside parameterized constructor");
    }

    public static void main(String[] args)
    {
        Test object = new Test();
    }
}
```

输出:

```java
Inside parameterized constructor
Inside  default constructor
```

**3。使用' this '关键字返回当前类实例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
//Java code for using 'this' keyword
//to return the current class instance
class Test
{
    int a;
    int b;

    //Default constructor
    Test()
    {
        a = 10;
        b = 20;
    }

    //Method that returns current class instance
    Test get()
    {
        return this;
    }

    //Displaying value of variables a and b
    void display()
    {
        System.out.println("a = " + a + "  b = " + b);
    }

    public static void main(String[] args)
    {
        Test object = new Test();
        object.get().display();
    }
}
```

输出:

```java
a = 10  b = 20
```

**4。使用' this '关键字作为方法参数**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code for using 'this'
// keyword as method parameter
class Test
{
    int a;
    int b;

    // Default constructor
    Test()
    {
        a = 10;
        b = 20;
    }

    // Method that receives 'this' keyword as parameter
    void display(Test obj)
    {
        System.out.println("a = " +obj.a + "  b = " + obj.b);
    }

    // Method that returns current class instance
    void get()
    {
        display(this);
    }

    public static void main(String[] args)
    {
        Test object = new Test();
        object.get();
    }
}
```

输出:

```java
a = 10  b = 20
```

**5。使用' this '关键字调用当前类方法**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code for using this to invoke current
// class method
class Test {

    void display()
    {
        // calling function show()
        this.show();

       System.out.println("Inside display function");
    }

    void show() {
        System.out.println("Inside show function");
    }

    public static void main(String args[]) {
        Test t1 = new Test();
        t1.display();
    }
}
```

输出:

```java
Inside show function
Inside display function
```

**6。在构造函数调用中使用“this”关键字作为参数**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code for using this as an argument in constructor
// call
// Class with object of Class B as its data member
class A
{
    B obj;

    // Parameterized constructor with object of B
    // as a parameter
    A(B obj)
    {
        this.obj = obj;

     // calling display method of class B
        obj.display();
    }

}

class B
{
    int x = 5;

    // Default Constructor that create a object of A
    // with passing this as an argument in the
   // constructor
    B()
    {
        A obj = new A(this);
    }

    // method to show value of x
    void display()
    {
        System.out.println("Value of x in Class B : " + x);
    }

    public static void main(String[] args) {
        B obj = new B();
    }
}
```

输出:

```java
Value of x in Class B : 5
```

本文由**迈哈克纳朗****艾米特·库马尔**供稿。

发现有不正确的地方请写评论，或者想分享更多以上讨论话题的信息。