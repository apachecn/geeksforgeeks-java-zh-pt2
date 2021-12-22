# 安卓中的 PopView

> 原文:[https://www.geeksforgeeks.org/popview-in-android/](https://www.geeksforgeeks.org/popview-in-android/)

本文在安卓中增加了 **PopView** 。当用户点击视图时，会出现一个带有圆形灰尘效果的流行动画。旧视图弹出后，也会出现新视图。 **PopView** 可用于隐藏视图或更改视图。它使用户界面更具吸引力。如果一个**启动器应用程序**将被制作，那么在该应用程序中关闭最近使用的应用程序，它可以使用。这个视图将帮助我们实现更好的用户体验。

### 方法:

**步骤 1:** 在 [**build.gradle**](https://www.geeksforgeeks.org/android-build-gradle/) 文件中添加支持库，并在依赖项部分添加依赖项。它将允许开发人员直接使用内置的功能。

## 可扩展标记语言

```

dependencies {     
      implementation 'rb.popview:popview:0.1.0'
}          
```