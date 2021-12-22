# Java 中的私有和最终方法

> 原文:[https://www . geesforgeks . org/private-and-final-methods-in-Java/](https://www.geeksforgeeks.org/private-and-final-methods-in-java/)

当我们在方法中使用*最终*说明符时，该方法不能在任何继承类中被重写。由于设计原因，方法是最终的。
因为私有方法是不可访问的，所以它们在 Java 中是隐式最终的。因此将*最终*说明符添加到私有方法中不会增加任何价值。事实上，这可能会造成不必要的混乱。

```java
class Base {

   private final void foo() {}

   // The above method foo() is same as following. The keyword 
   // final is redundant in above declaration.

   // private void foo() {}
}
```

例如，下面的“程序 1”和“程序 2”都会产生相同的编译器错误“foo()在 Base 中具有私有访问权限”。

**程序 1**

```java
// file name: Main.java
class Base {
    private final void foo() {}
}

class Derived extends Base {
    public void foo() {} 
}

public class Main {
    public static void main(String args[]) {
        Base b = new Derived();
        b.foo();
    }
}
```

**程序 2**

```java
// file name: Main.java
class Base {
    private void foo() {}
}

class Derived extends Base {
    public void foo() {} 
}

public class Main {
    public static void main(String args[]) {
        Base b = new Derived();
        b.foo();
    }
}
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。