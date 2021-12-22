# 用 Java 中“main”中的“private”替换“public”

> 原文:[https://www . geesforgeks . org/用 java 中的 main-in-private 替换-public-in-main/](https://www.geeksforgeeks.org/replacing-public-with-private-in-main-in-java/)

考虑以下 Java 程序:

```
class GFG {
    public static void main(String args[])
    {
        System.out.println("GeeksforGeeks");
    }
}
```

```
GeeksforGeeks
```

**解释:**
1) **公共**:是一个访问说明符，允许 JVM(Java 虚拟机)从任何地方访问主方法。
2) **static** : static 关键字允许 JVM 在没有任何实例(对象)的情况下访问主方法。
3) **void** :指定主方法不返回任何东西。
4)**main**:JVM 中配置的方法(函数)名称。
5) **字符串参数[]** :命令行参数。

现在，如果我们将“公共静态 void main”中的“public”替换为“private”，上面的代码将变成:

```
class GFG {
    private static void main(String args[])
    {
        System.out.println("GeeksforGeeks");
    }
}
```

**解释:**
上面的代码会编译成功，但是会抛出如下运行时错误:

```
Error: Main method not found in class GFG, please define the main method as:
   public static void main(String[] args)
or a JavaFX application class must extend javafx.application.Application

```

[点击查看输出](https://ide.geeksforgeeks.org/1xiyRfzF0W)

**原因:**由于访问说明符从“公共”更改为“私有”，JVM 无法访问/定位主方法。