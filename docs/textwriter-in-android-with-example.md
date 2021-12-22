# 安卓中的 TextWriter，示例

> 原文:[https://www . geesforgeks . org/text writer-in-Android-with-example/](https://www.geeksforgeeks.org/textwriter-in-android-with-example/)

**TextWriter** 用于文本动画。当用户打开应用程序时，可以使用文本书写器来代替[闪屏](https://www.geeksforgeeks.org/android-creating-a-splash-screen/)。人们也可以使用闪屏来代替文本编写器，但是文本编写器是一个动画库，众所周知，动画有助于获得用户的注意，所以最好学习它。文本书写器可以根据需要定制，如文本颜色、文本大小、字母间距等。
![text-writer](img/449c651e26b446a33f339c8069fa299a.png)

#### 方法

*   **第一步:**在根 **[build.gradle](https://www.geeksforgeeks.org/android-build-gradle/)** 文件中添加支持库(不在模块 build.gradle 文件中)。这个库 **jitpack** 是一个新颖的包库。它是为 JVM 而做的，因此 [github](https://www.geeksforgeeks.org/ultimate-guide-git-github/) 和 [bigbucket](https://www.geeksforgeeks.org/bitbucket-vs-github-vs-gitlab/) 中存在的任何库都可以直接在应用程序中使用。

    ```
    allprojects {           
     repositories {           
            maven { url 'https://jitpack.io' }           
         }          
    }           
    ```

*   **第二步:**在 **[build.gradle](https://www.geeksforgeeks.org/android-build-gradle/)** 文件中添加支持库，并在依赖项部分添加依赖项。

    ```
    implementation 'com.github.sarnavakonar:TextWriter:v1.0'          
    ```

*   **第三步:**在 **activity_main.xml** 文件中添加以下代码。在此文件中，将**文本编写器**添加到布局中。

    ## activity _ main . XML

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <androidx.constraintlayout.widget.ConstraintLayout
        xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:app="http://schemas.android.com/apk/res-auto"
        android:layout_width="match_parent"
        android:layout_height="match_parent">

    <com.sarnava.textwriter.TextWriter
        android:id="@+id/textWriter"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        xmlns:android="http://schemas.android.com/apk/res/android"
        />     

    </androidx.constraintlayout.widget.ConstraintLayout>
    ```

*   **步骤 4:** 在**MainActivity.java**文件中添加以下代码。在该文件中添加**文本编写器**的重要标签，并添加一个 **`setListner()`** ，当**文本编写器**编写完整个文本后，会自动调用该标签。T57】MainActivity.javaT59T4T62T64

    #### 输出：在模拟器上运行

    <video class="wp-video-shortcode" id="video-460483-1" width="320" height="540" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200718150941/VID_202007181506161.mp4?_=1">[https://media . geekesforgeks . org/WP-content/uploads/20200718150941/VID _ 202007181506161 . MP4](https://media.geeksforgeeks.org/wp-content/uploads/20200718150941/VID_202007181506161.mp4)</video>