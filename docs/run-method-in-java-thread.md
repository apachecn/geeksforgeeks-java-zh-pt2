# 在 Java 线程中运行()方法

> 原文:[https://www.geeksforgeeks.org/run-method-in-java-thread/](https://www.geeksforgeeks.org/run-method-in-java-thread/)

run()方法在使用单独的 Runnable 对象构造的线程类中可用。否则，此方法不执行任何操作并返回。我们可以多次调用 run()方法。

**run()方法有两种调用方式，如下所示:**

1.  使用 start()方法。
2.  使用 run()方法本身。

**语法:**

```
public void run()  
{    
    //statements  
}  
```

### **1。使用 start()方法**

我们可以通过使用线程对象来使用 start()方法。

**步骤 1:** 创建运行方法。

**步骤 2:** 为类创建一个对象。

```
Syntax: Usingstart obj=new Usingstart(); 
```

**步骤 3:** 通过传递类变量创建线程对象。

```
Syntax: Thread t1 =new Thread(obj);    
```

**第 4 步:**这将调用 run()方法。

```
Syntax: t1.start();
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the working 
// of run() method using the start() method

public class Usingstart implements Runnable  
{    
    //run method
    public void run()  
    {    
        System.out.println("This thread is running");    
    }    

    //main method
    public static void main(String args[])  
    { 
        //create the object
        Usingstart obj=new Usingstart(); 

        //create thread object by passing the class variable
        Thread t1 =new Thread(obj);    

        // this will call run() method   
        t1.start();    
    }    
}
```

**Output**

```
This thread is running
```

### **2。使用 run()方法**

我们可以通过使用线程对象来使用 run()方法。

**步骤 1:** 创建运行方法。

**步骤 2:** 为类创建一个对象。

```
Syntax: Usingstart obj=new Usingstart();     
```

**第三步:**这将调用 run()方法。

```
Syntax: obj.run();
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate 
// the working of run() method

public class Usingstart implements Runnable  
{    
    //run method
    public void run()  
    {    
        System.out.println("This thread is running");    
    }    

    //main method
    public static void main(String args[])  
    { 
        //create the object
        Usingstart obj=new Usingstart(); 

        // this will call run() method   
        obj.run();    
    }    
}
```

**Output**

```
This thread is running
```

### 多次调用 run()方法

在 Java 中，我们还可以多次调用 run()方法。通过使用 for 循环，我们可以多次调用同一个 run 方法。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to call the
// run() method multiple times

public class RumMultipleTimes extends Thread {
    public void run()
    {
        // run 10 times each
        for (int i = 1; i <= 10; i++) {
            System.out.println("Running " + i + " Time");
        }
    }

    public static void main(String args[])
    {
        // create object
        RumMultipleTimes t1 = new RumMultipleTimes();

        // call the run method
        t1.run();
        t1.run();
    }
}
```

**Output**

```
Running 1 Time
Running 2 Time
Running 3 Time
Running 4 Time
Running 5 Time
Running 6 Time
Running 7 Time
Running 8 Time
Running 9 Time
Running 10 Time
Running 1 Time
Running 2 Time
Running 3 Time
Running 4 Time
Running 5 Time
Running 6 Time
Running 7 Time
Running 8 Time
Running 9 Time
Running 10 Time
```

### 重载 run()方法

我们也可以重载 run()方法。通过改变参数，我们可以从方法中得到精确的东西。

**示例:**采用两个重载方法的 Java 程序，一个带参数，另一个不带参数。

这里我们首先调用参数方法，然后调用无参数方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate the behavior of
// run() method overloading

class GFG extends Thread {

    // run method with no parameters
    public void run()
    {
        System.out.println("no parameters method");
    }

    // run method with  parameters
    public void run(int i)
    {
        System.out.println("single parameter method");
    }
}

public class Test {
    public static void main(String[] args)
    {
        // create an object
        GFG t = new GFG();

        // call the parameter method
        t.run(8);

        // call the no parameter method
        t.run();
    }
}
```

**Output**

```
single parameter method
no parameters method
```