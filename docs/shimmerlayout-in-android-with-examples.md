# 安卓中闪烁视频示例

> 原文:[https://www . geeksforgeeks . org/shimmerlayut-in-Android-with-examples/](https://www.geeksforgeeks.org/shimmerlayout-in-android-with-examples/)

**微光游**可以用来给安卓应用增加一个**微光效果**(就像 **[【脸书】](https://www.geeksforgeeks.org/tag/facebook/)** 或者 **[LinkedIn](https://www.geeksforgeeks.org/tag/linkedin/)** 的那个)。这种布局主要用于应用程序从应用程序接口获取数据，但任务是长期运行的任务。因此，最好添加**微光布局**而不是显示空白屏幕，因为它通知用户布局处于加载状态。

**优势:**

*   ShimmerLayout 是内存高效的。
*   可以根据应用的需要进行定制。

**劣势:**

*   不推荐使用。

**进场:**

1.  在 **[build.gradle](https://www.geeksforgeeks.org/android-build-gradle/)** 文件中添加支持库，并在依赖项部分添加依赖项。它允许开发人员直接使用内置功能。

    ```java

    dependencies {     
          implementation 'io.supercharge:shimmerlayout:2.1.0'
    }          
    ```

2.  在可绘制文件夹中创建 **circle.xml** 文件，并添加以下代码。这将与 textview 一起在 ShimmerLayout 中使用。

    ## 

    ```java
    <?xml version="1.0" encoding="utf-8"?>
    <shape xmlns:android="http://schemas.android.com/apk/res/android"
        android:shape="rectangle">
        <size
            android:height="40dp"
            android:width="40dp"/>
        <corners android:radius="20dp"/>
        <solid android:color="#D3D3D3"/>
    </shape>
    ```

3.  在 **activity_main.xml** 文件中添加以下代码。在该文件中，添加**微光视频**及其子视图。添加圆圈。ImageView 中 **src** 标签中的 XML。

    ## activity _ main . XML

    ```java

    <io.supercharge.shimmerlayout.ShimmerLayout
        xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:app="http://schemas.android.com/apk/res-auto"
        android:id="@+id/shimmer_layout"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        app:shimmer_animation_duration="2000">
        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:orientation="vertical">
            <LinearLayout
                android:layout_marginTop="5dp"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:orientation="horizontal">
                <ImageView
                    android:layout_marginStart="10dp"
                    android:src="@drawable/circle"
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_marginEnd="10dp"
                    />
                <TextView
                    android:layout_marginEnd="10dp"
                    android:layout_width="match_parent"
                    android:layout_height="40dp"
                    android:gravity="center"
                    android:background="#D3D3D3"
                    android:textSize="26sp"/>
            </LinearLayout>
            <LinearLayout
                android:layout_marginTop="10dp"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:orientation="horizontal">
                <ImageView
                    android:layout_marginStart="10dp"
                    android:src="@drawable/circle"
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_marginEnd="10dp"
                    />
                <TextView
                    android:layout_marginEnd="10dp"
                    android:layout_width="match_parent"
                    android:layout_height="40dp"
                    android:gravity="center"
                    android:background="#D3D3D3"
                    android:textSize="26sp"/>
            </LinearLayout>
            <LinearLayout
                android:layout_marginTop="10dp"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:orientation="horizontal">
                <ImageView
                    android:layout_marginStart="10dp"
                    android:src="@drawable/circle"
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_marginEnd="10dp"
                    />
                <TextView
                    android:layout_marginEnd="10dp"
                    android:layout_width="match_parent"
                    android:layout_height="40dp"
                    android:gravity="center"
                    android:background="#D3D3D3"
                    android:textSize="26sp"/>
            </LinearLayout>
        </LinearLayout>
    </io.supercharge.shimmerlayout.ShimmerLayout>
    ```

4.  在**MainActivity.java**文件中添加以下代码。在这个文件中，**开始微光动画**方法用于在微光视频上开始动画。

    ## MainActivity.java

    ```java
    package org.geeksforgeeks.shimmerLayout;

    import android.os.Bundle;
    import android.view.View;
    import android.widget.Button;
    import androidx.annotation.Nullable;
    import androidx.appcompat.app.AppCompatActivity;
    import io.supercharge.shimmerlayout.ShimmerLayout;

    public class MainActivity
        extends AppCompatActivity {

        @Override
        protected void onCreate(
            @Nullable Bundle savedInstanceState)
        {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_main);

            ShimmerLayout layout = findViewById(
                R.id.shimmer_layout);
            layout.startShimmerAnimation();
        }
    }
    ```

    **Output:**

    <video class="wp-video-shortcode" id="video-458772-1" width="320" height="540" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200719214545/Record_2020-07-19-21-23-01_69fa71ed7e998de6cab47c8740bea3c11.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200719214545/Record_2020-07-19-21-23-01_69fa71ed7e998de6cab47c8740bea3c11.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200719214545/Record_2020-07-19-21-23-01_69fa71ed7e998de6cab47c8740bea3c11.mp4)</video>

    **Reference:**

    [https://github.com/team-supercharge/ShimmerLayout](https://github.com/team-supercharge/ShimmerLayout)