# 安卓共享元素过渡示例

> 原文:[https://www . geesforgeks . org/shared-element-transition-in-Android-with-example/](https://www.geeksforgeeks.org/shared-element-transition-in-android-with-example/)

**共享元素过渡**是安卓应用中最常见的动画之一。当我们必须从[列表视图](https://www.geeksforgeeks.org/android-listview-in-java-with-example/)或[回收视图](https://www.geeksforgeeks.org/android-recyclerview/)中打开一个项目时，会使用这种类型的动画。安卓中的共享元素过渡决定了共享元素视图如何从一个活动到另一个活动或者从一个片段到另一个片段进行动画制作。现在，我们将通过一个简单的例子在我们的应用程序中看到共享元素转换的实现。

## 安卓系统中共享元素转换的实现

在本例中，我们将创建一个简单的应用程序，其中我们将使用 [ImageView](https://www.geeksforgeeks.org/imageview-in-kotlin/) 创建两个活动，并在这两个活动之间实现过渡动画。下面给出了一个示例 GIF，以了解我们将在本文中做什么。请注意，我们将使用 **Java** 语言来实现这个项目。

![Shared Element Transition in Android Sample GIf](img/3e27fcdb932d51ee6812f78ab28c6b0a.png)

### 逐步实施

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:创建新的空活动**

导航至**应用程序> java >您的包名称>右键单击>新建>活动>清空活动**并将活动命名为**主要活动 2** 。

**步骤 3:使用 activity_main.xml 文件**

转到 **activity_main.xml** 文件，参考以下代码。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--Transition name is a simple
        string that will be given
        to two views between which
         we are applying transition-->

    <!--Transition name should be same
         for both the views in which we
        are making transition-->

    <ImageView
        android:id="@+id/image"
        android:layout_width="180dp"
        android:layout_height="100dp"
        android:layout_alignParentBottom="true"
        android:layout_centerHorizontal="true"
        android:layout_marginBottom="120dp"
        android:contentDescription="@string/image_desc"
        android:scaleType="centerCrop"
        android:src="@drawable/gfgimage"
        android:transitionName="fade" />

</RelativeLayout>
```

**第 4 步:使用 activity_main2.xml 文件**

转到 **activity_main2.xml** 文件，参考以下代码。下面是 **activity_main2.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity2">

    <!--Transition name is same
        as that we have used
        in previous imageview-->

    <ImageView
        android:layout_width="match_parent"
        android:layout_height="250dp"
        android:layout_alignParentTop="true"
        android:contentDescription="@string/image_desc"
        android:scaleType="centerCrop"
        android:src="@drawable/gfgimage"
        android:transitionName="fade" />

</RelativeLayout>
```

**步骤 5:使用 MainActivity2.java 文件**

转到**MainActivity2.java**文件，参考以下代码。以下是**MainActivity2.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.os.Build;
import android.os.Bundle;
import android.transition.Fade;
import android.view.View;

import androidx.annotation.RequiresApi;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity2 extends AppCompatActivity {

    @RequiresApi(api = Build.VERSION_CODES.LOLLIPOP)
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main2);

        // here we are initializing
        // fade animation.
        Fade fade = new Fade();
        View decor = getWindow().getDecorView();

        // here also we are excluding status bar,
        // action bar and navigation bar from animation.
        fade.excludeTarget(decor.findViewById(R.id.action_bar_container), true);
        fade.excludeTarget(android.R.id.statusBarBackground, true);
        fade.excludeTarget(android.R.id.navigationBarBackground, true);

        // below methods are used for adding
        // enter and exit transition.
        getWindow().setEnterTransition(fade);
        getWindow().setExitTransition(fade);
    }
}
```

**步骤 6:使用 MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.Intent;
import android.os.Build;
import android.os.Bundle;
import android.transition.Fade;
import android.view.View;
import android.widget.ImageView;

import androidx.annotation.RequiresApi;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.app.ActivityOptionsCompat;
import androidx.core.view.ViewCompat;

public class MainActivity extends AppCompatActivity {

    @RequiresApi(api = Build.VERSION_CODES.LOLLIPOP)
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // we are adding fade animation
        // between two imageviews.
        Fade fade = new Fade();
        View decor = getWindow().getDecorView();

        // below 3 lines of code is to exclude
        // action bar,title bar and navigation
        // bar from animation.
        fade.excludeTarget(decor.findViewById(R.id.action_bar_container), true);
        fade.excludeTarget(android.R.id.statusBarBackground, true);
        fade.excludeTarget(android.R.id.navigationBarBackground, true);

        // we are adding fade animation
        // for enter transition.
        getWindow().setEnterTransition(fade);

        // we are also setting fade
        // animation for exit transition.
        getWindow().setExitTransition(fade);

        // initializing our imageview.
        final ImageView imageView = findViewById(R.id.image);

        // setting on click listener for our imageview.
        imageView.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // on image click we are opening new activity
                // and adding animation between this two activities.
                Intent intent = new Intent(MainActivity.this, MainActivity2.class);
                // below method is used to make scene transition
                // and adding fade animation in it.
                ActivityOptionsCompat options = ActivityOptionsCompat.makeSceneTransitionAnimation(
                        MainActivity.this, imageView, ViewCompat.getTransitionName(imageView));
                // starting our activity with below method.
                startActivity(intent, options.toBundle());
            }
        });
    }
}
```

### 输出:

<video class="wp-video-shortcode" id="video-530249-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201215184525/Screenrecorder-2020-12-15-18-36-30-861.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201215184525/Screenrecorder-2020-12-15-18-36-30-861.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201215184525/Screenrecorder-2020-12-15-18-36-30-861.mp4)</video>

**出库应用程式码:**[https://github . com/chaitanyamunje/gfgimanaguider/tree/shared element transference](https://github.com/ChaitanyaMunje/GFGImageSlider/tree/SharedElementTransition)