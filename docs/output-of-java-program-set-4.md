# Java 程序输出|第 4 集

> 原文:[https://www.geeksforgeeks.org/output-of-java-program-set-4/](https://www.geeksforgeeks.org/output-of-java-program-set-4/)

预测以下 Java 程序的输出:

**问题 1**

```
// file name: Main.java

class Base {
    protected void foo() {}
} 
class Derived extends Base {
    void foo() {}
} 
public class Main {
    public static void main(String args[]) {
        Derived d = new Derived();
        d.foo();
    }
}
```

输出:编译器错误
foo()在 Base 中受保护，在派生类中默认。默认访问权限更严格。当一个派生类重写一个基类函数时，不能给被重写的函数更严格的访问权限。如果我们将 foo()公之于众，那么程序就可以正常运行，没有任何错误。C++中的行为是不同的。 [C++允许对派生类方法进行更严格的访问。](https://www.geeksforgeeks.org/what-happens-when-more-restrictive-access-is-given-in-a-derived-class-method-in-c/)

**问题 2**

```
// file name: Main.java

class Complex {
    private double re, im;    
    public String toString() {
        return "(" + re + " + " + im + "i)";
    }
    Complex(Complex c) {
        re = c.re;
        im = c.im;
    }
}

public class Main {
    public static void main(String[] args) {
        Complex c1 = new Complex();
        Complex c2 = new Complex(c1);
        System.out.println(c2);
    }
}
```

输出:第行“复杂 c1 =新复杂()”中的编译器错误
在 Java 中，如果我们自己编写[复制构造函数](https://www.geeksforgeeks.org/copy-constructor-in-java/)或者参数化构造函数，那么编译器不会创建默认的构造函数。这种行为与 C++相同。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。