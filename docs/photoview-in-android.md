# 安卓中的 PhotoView

> 原文:[https://www.geeksforgeeks.org/photoview-in-android/](https://www.geeksforgeeks.org/photoview-in-android/)

本文在安卓中增加了 **PhotoView** 。 **PhotoView** 旨在通过多点触控和双击，帮助制作一个易于使用的变焦安卓 **ImageView** 实现。除此之外，它还有更多功能，比如当用户点击照片或显示的矩阵发生变化时，它会通知应用程序。它提供了平滑的滚动，即使使用了像 ViewPager 这样的滚动父容器。可以在图库应用中使用。
**进场:**

**步骤 1:** 在你的根[中添加支持库**build.gradle**T5】文件(不是你的模块 build . gradle 文件)。这个库 **jitpack** 是一个新颖的包存储库。它是为 JVM 而做的，这样在](https://www.geeksforgeeks.org/android-build-gradle/) [github](https://www.geeksforgeeks.org/ultimate-guide-git-github/) 和 [bigbucket](https://www.geeksforgeeks.org/bitbucket-vs-github-vs-gitlab/) 中存在的任何库都可以直接在应用程序中使用。

## 可扩展标记语言

```java

allprojects {           
 repositories {           
        maven { url 'https://jitpack.io' }           
     }          
}           
```

**第二步:**在 [**build.gradle**](https://www.geeksforgeeks.org/android-build-gradle/) 文件中添加支持库，并在依赖项部分添加依赖项。它允许开发人员在 XML 文件中直接使用照片视图。

## 可扩展标记语言

```java

dependencies {           
     implementation 'com.github.chrisbanes:PhotoView:2.0.0'          
}          
```

**第三步:**在 **activity_main.xml** 文件中添加以下代码。在该文件中，**照片视图**被添加到布局中。

## activity_main.xml

```java

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <com.github.chrisbanes.photoview.PhotoView
        android:id="@+id/photo_view"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>

</androidx.constraintlayout.widget.ConstraintLayout>    
```

**第 4 步:**在**MainActivity.java**文件中添加以下代码。在这个文件中，我们将图像添加到我们的**照片视图**中。 **setImageResource()** 方法用于在 PhotoView 中添加图像。

## MainActivity.java

```java

package org.geeksforgeeks.photoView          

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import com.github.chrisbanes.photoview.PhotoView;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        PhotoView photoView = (PhotoView)
                  findViewById(R.id.photo_view);
        photoView.setImageResource(R.drawable.gfg);

    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-454511-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200715135622/2020_07_15_13_53_53_trim1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200715135622/2020_07_15_13_53_53_trim1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200715135622/2020_07_15_13_53_53_trim1.mp4)</video>

*更多信息请参考* [*官方文档*](https://github.com/chrisbanes/PhotoView) *。*