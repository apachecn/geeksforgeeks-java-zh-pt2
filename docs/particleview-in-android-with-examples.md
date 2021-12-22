# 安卓中的粒子视图，带示例

> 原文:[https://www . geeksforgeeks . org/piece view-in-Android-with-examples/](https://www.geeksforgeeks.org/particleview-in-android-with-examples/)

**粒子视图**是一个动画库，动画有助于获得用户的关注，所以最好学习一下。这是定制的安卓视图，有助于显示大量的仙女。
T3】

#### 为什么是粒子视图？

*   粒子视图提供预定义的布局类型和动画。
*   粒子视图可以在 [**闪屏**中使用。](https://www.geeksforgeeks.org/android-creating-a-splash-screen/#:~:text=A%20splash%20screen%20is%20mostly,when%20the%20app%20is%20launched.)
*   最好使用粒子视图，因为它的用户界面，因为一个好的用户界面在应用程序中起着非常重要的作用。

#### 方法

*   **第一步:**在根 **[build.gradle](https://www.geeksforgeeks.org/android-build-gradle/)** 文件中添加支持库(不在模块 build.gradle 文件中)。

    ```java
    allprojects {           
     repositories {           
           maven { url 'https://dl.bintray.com/wangyuwei/maven' }           
         }          
    }           
    ```

*   **第二步:**在 **[build.gradle](https://www.geeksforgeeks.org/android-build-gradle/)** 文件中添加支持库，并在依赖项部分添加依赖项。

    ```java
    implementation 'me.wangyuwei:ParticleView:1.0.4'      
    ```

*   **第三步:**在 **activity_main.xml** 文件中添加以下代码。在此文件中，将**粒子视图**添加到布局中。

    ## activity _ main . XML

    ```java

    <?xml version="1.0" encoding="utf-8"?>
    <LinearLayout
        android:background="@color/grey"
        xmlns:android="http://schemas.android.com/apk/res/android"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        xmlns:pv="http://schemas.android.com/apk/res-auto"
        android:orientation="vertical"
        android:gravity="center">

        <me.wangyuwei.particleview.ParticleView
            android:id="@+id/particleView"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            pv:pv_host_text="GeeksForGeeks"
            pv:pv_host_text_size="32sp"
            pv:pv_particle_text=".com"
            pv:pv_particle_text_size="18sp"
            pv:pv_text_color="@color/colorPrimary"
            pv:pv_background_color="#FFF"
            pv:pv_text_anim_time="2000"
            pv:pv_spread_anim_time="300"
            pv:pv_host_text_anim_time="1000" />

    </LinearLayout>
    ```

*   **步骤 4:** 在**文件中添加以下代码。在此文件中添加 **`ParticleAnimationListner()`** ，动画结束时会自动调用。

    ## MainActivity.java

    ```java
    package org.geeksforgeeks.particleView          

    import android.os.Bundle;
    import android.view.View;
    import android.widget.Toast;
    import androidx.annotation.Nullable;
    import androidx.appcompat.app.AppCompatActivity;
    import me.wangyuwei.particleview.ParticleView;

    public class MainActivity extends AppCompatActivity {

        ParticleView particleView;
        @Override
        protected void onCreate(@Nullable Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_main);

            particleView = findViewById(R.id.particleView);
            particleView.startAnim();

            // this listner will get invoked automatically
            // when animaion ends.
            particleView.setOnParticleAnimListener(
                    new ParticleView.ParticleAnimListener() {
                @Override
                public void onAnimationEnd() {
                    Toast.makeText(MainActivity.this,
                            "Animation is End!!", 
                             Toast.LENGTH_SHORT).show();
                }
            });
        }
    }
    ```

    #### 输出：在模拟器上运行

    <video class="wp-video-shortcode" id="video-460125-1" width="320" height="540" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200723030131/VID_202007230258461.mp4?_=1">[https://media . geeksforgeeks . org/WP-content/uploads/20200723030131/VID _ 202007230258461 . MP4](https://media.geeksforgeeks.org/wp-content/uploads/20200723030131/VID_202007230258461.mp4)</video>**