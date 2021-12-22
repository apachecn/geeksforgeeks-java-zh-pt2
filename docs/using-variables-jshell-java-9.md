# 在 Java 9 的 JShell 中使用变量

> 原文:[https://www . geesforgeks . org/using-variables-jshell-Java-9/](https://www.geeksforgeeks.org/using-variables-jshell-java-9/)

先决条件:[Java 9 中的 JShell](https://www.geeksforgeeks.org/jshell-java-9-new-feature/)

我们可以在整个 Jshell 会话中声明变量并在任何地方使用。让我们创建一个
整数变量。

![jshell variable  example](img/5da7dcbe20d27d5d559683c3a0f4f2aa.png)

分号(；)是可选的，我们可以离开它，它工作得很好。看，变量 b 是不用分号创建的。

![jshell variable ](img/7653d91b61c4c05dc8ce33dd2b2ecfce.png)

##### 临时变量

如果我们不提供变量名，Java 创建隐式变量来存储值。这些变量以$符号开始。我们可以通过指定隐式变量来使用这些变量，就像我们在下面的屏幕截图中所做的那样。

![jhsell variable ](img/a6416b9a0e71ddad8fadcb4d08dfd394.png)

#### 公式

我们可以测试任何有效的 Java 表达式来获得即时输出。请看下面的例子。
**两个整数相加**
![jshell add](img/66389ad803b9cf74c5f3e00551baeabf.png)

**复合词**
![](img/ad4c8348bf739de352089435f5eeff83.png)

**创建和调用方法**
要测试方法业务逻辑，创建一个方法并立即得到结果。请参见以下示例

![jshell method](img/bfbf6550a61c654b14980a023578d0c9.png)

![jshell calling](img/451b17d97834c78bcf5db4c7b04adb74.png)