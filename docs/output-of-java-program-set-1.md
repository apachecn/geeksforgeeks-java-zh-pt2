# Java 程序输出|设置 1

> 原文:[https://www.geeksforgeeks.org/output-of-java-program-set-1/](https://www.geeksforgeeks.org/output-of-java-program-set-1/)

**难度等级:**菜鸟

预测以下 Java 程序的输出。

**程序 1**

```
// filename Main.java
class Test {
    protected int x, y;
}

class Main {
    public static void main(String args[]) {
        Test t = new Test();
        System.out.println(t.x + " " + t.y);
    }
}
```

输出

```
0 0
```

在 Java 中，受保护的成员可以在同一个包的所有类和其他包的继承类中访问。因为 Test 和 Main 在同一个包中，所以在上面的程序中没有访问相关的问题。另外，缺省构造函数在 Java 中将整型变量初始化为 0(更多细节参见[本](https://www.geeksforgeeks.org/g-fact-50/) GFact)。这就是为什么我们得到的输出是 0 0。

**节目 2**

```
// filename Test.java
class Test {
    public static void main(String[] args) {
        for(int i = 0; 1; i++) {
            System.out.println("Hello");
            break;
        }
    }
}
```

输出:编译器错误
for 循环的条件检查表达式有错误。Java 在这里不同于 C++(或 C)。C++认为所有非零值为真，0 为假。与 C++不同，在 Java 中，整数值表达式不能放在需要布尔值的地方。以下是修正后的程序。

```
// filename Test.java
class Test {
    public static void main(String[] args) {
        for(int i = 0; true; i++) {
            System.out.println("Hello");
            break;
        }
    }
}
// Output: Hello
```

**节目 3**

```
// filename Main.java
class Main {
    public static void main(String args[]) {   
        System.out.println(fun());
    } 
    int fun() {
        return 20;
    } 
}
```

输出:编译器错误
和 C++一样，在 Java 中，非静态方法不能在静态方法中调用。如果我们取笑()静态，那么程序编译良好，没有任何编译器错误。以下是修正后的程序。

```
// filename Main.java
class Main {
    public static void main(String args[]) {
        System.out.println(fun());
    } 
    static int fun() {
        return 20;
    }
}
// Output: 20
```

**节目 4**

```
// filename Test.java
class Test {
   public static void main(String args[]) {
       System.out.println(fun());
   }
   static int fun() {
       static int x= 0;
       return ++x;
   }
}
```

输出:编译器错误
与 C++不同，Java 中不允许静态局部变量。详见[本](https://www.geeksforgeeks.org/g-fact-47/) GFact。我们可以让类静态成员来计算函数调用的数量，以及 C++局部静态变量服务的其他目的。以下是修正后的程序。

```
class Test {
   private static int x;
   public static void main(String args[]) {
       System.out.println(fun());
   }
   static int fun() {
       return ++x;
   }
}
// Output: 1
```

如果您发现任何答案/解释不正确，或者想分享更多关于上述主题的信息，请写评论。