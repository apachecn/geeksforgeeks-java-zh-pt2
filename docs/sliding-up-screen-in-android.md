# 在安卓中向上滑动屏幕

> 原文:[https://www.geeksforgeeks.org/sliding-up-screen-in-android/](https://www.geeksforgeeks.org/sliding-up-screen-in-android/)

**向上滑动屏幕**是我们在大多数应用中看到的另一个常见功能。此向上滑动屏幕可用于在单击按钮后显示一些内容或显示菜单。在我们的应用程序中使用这种向上滑动屏幕可以改善用户体验。在本文中，我们将看到如何在安卓系统中实现向上滑动屏幕。下面给出了一个示例 GIF，以了解我们将在本文中做什么。

![Sliding Up Screen in Android Sample GIF](img/66e140b124e5c9c97b411220340ae7e7.png)

### 向上滑动屏幕的应用

*   向上滑动屏幕可用于在以另一种吸引人的形式单击按钮后显示一些内容。
*   该向上滑动屏幕也可用于显示附加菜单选项。
*   在我们的应用程序中使用向上滑动屏幕可以改善用户体验。

### 向上滑动屏幕的属性

<figure class="table">

| 

属性

 | 

描述

 |
| --- | --- |
| **布局 _ 宽度** | 用于给出布局宽度。 |
| **布局 _ 高度** | 用于给出布局高度。 |
| **重力** | 用来产生重力。 |
| **人体八** | 用于给面板赋予高度。 |
| 人性化监督 | 用于显示阴影高度。 |

</figure>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在 build.gradle 文件**中添加上滑屏幕库的依赖关系

然后导航到渐变脚本，然后导航到**构建.渐变(模块)**级别。在依赖项部分的 [build.gradle](https://www.geeksforgeeks.org/android-build-gradle/) 文件中添加以下行。

> 实现' com . sotree . sliding uppanel:library:3 . 4 . 0 '

现在点击**立即同步**它将同步你在 **build.gradle()** 中的所有文件。

**第三步:在你的 activity_main.xml 文件中创建一个新的向上滑动屏幕**

导航到**应用程序> res >** 布局，打开 **activity_main.xml** 文件。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:paddingLeft="16dp"
    android:paddingTop="16dp"
    android:paddingRight="16dp"
    android:paddingBottom="16dp"
    tools:context=".MainActivity">

    <!--Sliding Up Screen-->
    <com.sothree.slidinguppanel.SlidingUpPanelLayout 
        xmlns:sothree="http://schemas.android.com/apk/res-auto"
        android:id="@+id/sliding_layout"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:gravity="bottom"
        sothree:umanoPanelHeight="68dp"
        sothree:umanoShadowHeight="4dp">

        <!--First Screen-->
        <include
            layout="@layout/layout_first"
            android:layout_width="match_parent"
            android:layout_height="match_parent" />

        <!--Second Screen-->
        <include
            layout="@layout/layout_second"
            android:layout_width="match_parent"
            android:layout_height="match_parent" />
    </com.sothree.slidinguppanel.SlidingUpPanelLayout>

</RelativeLayout>
```

**第四步:在布局文件夹**中创建屏幕 1 和屏幕 2

导航到**应用程序> res >布局**并在布局文件夹中创建 **layout_first.xml** 和 **layout_second.xml** 文件。遵循下面给出的代码。

**layout_first.xml 文件:**

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:layout_gravity="center"
    android:gravity="center"
    android:orientation="vertical">

    <!--Text view to display text-->
    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="This is First Screen" />

    <!--Button for click-->
    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Click" />

</LinearLayout>
```

**layout_second.xml 文件:**

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:layout_gravity="center"
    android:gravity="center"
    android:orientation="vertical">

    <!--Text view to display text-->
    <TextView
        android:id="@+id/textView2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="This is Second Screen" />

    <!--Button for click-->
    <Button
        android:id="@+id/button2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Click Again" />

</LinearLayout>
```

现在点击**运行**选项**构建梯度**需要一些时间。之后，您将获得如下所示的设备输出。

### **输出:**

<video class="wp-video-shortcode" id="video-554560-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210129160046/Screenrecorder-2021-01-29-15-56-41-412.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210129160046/Screenrecorder-2021-01-29-15-56-41-412.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210129160046/Screenrecorder-2021-01-29-15-56-41-412.mp4)</video>