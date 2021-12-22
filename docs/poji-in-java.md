# Java 中的 POJI

> 原文:[https://www.geeksforgeeks.org/poji-in-java/](https://www.geeksforgeeks.org/poji-in-java/)

**POJI:** 代表普通老 Java 接口。POJI 是一个没有任何特长的普通接口。不从技术/框架特定接口扩展的接口。例如，所有用户定义的接口都是 POJI，从 Java Beans 的 AppletInitializer 继承的接口不是 POJI。
例子:

## Java 语言（一种计算机语言，尤用于创建网站）

```
// A POJI interface
interface GFG {
  public void method1();
}

interface Geeks extends GFG {
  public void method2();
}
```

**说明:**这里 GFG 和极客这两个界面本质上都是 POJI。因为 GFG 和极客都没有从任何特定于技术的界面延伸出来。

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Another POJI interface
interface GFG extends java.io.Serializable {

}
```