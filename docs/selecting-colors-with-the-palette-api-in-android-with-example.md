# 在安卓中使用调色板 API 选择颜色，示例

> 原文:[https://www . geeksforgeeks . org/用调色板选择颜色-带示例的安卓 API/](https://www.geeksforgeeks.org/selecting-colors-with-the-palette-api-in-android-with-example/)

当我们为任何应用程序进行用户界面设计时，在构建应用程序时，我们应该注意的最重要的部分是，我们应该在应用程序中使用适当的颜色组合，这些颜色组合有时应该与图像的颜色组合相同。使用这个应用编程接口，我们可以根据图像中呈现的颜色来更新小部件的颜色。这个应用编程接口将帮助我们从图像中提取颜色，然后我们可以在小部件中使用这些颜色。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将使用两个不同的图像来根据我们的图像文件更改我们的布局用户界面组件颜色。下面给出一个视频样本，了解一下在本文中我们要做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-591537-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210408143913/20210408_143820.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210408143913/20210408_143820.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210408143913/20210408_143820.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在 build.gradle 文件**中添加依赖关系

导航至 **Gradle 脚本> build.gradle(模块:app)** 并在依赖项部分添加以下依赖项。

> 实现' com . Android . support:palette-v 7:30 . 3 . 0 '

添加依赖项后，现在同步您的项目，我们将继续使用布局文件。

**步骤 3:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/idRLBack"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <!--Image view for displaying our image-->
    <ImageView
        android:id="@+id/idIVImage"
        android:layout_width="200dp"
        android:layout_height="200dp"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="70dp"
        android:src="@drawable/logo1" />

    <!--linear layout for our buttons to 
        change image and layout colors-->
    <LinearLayout
        android:id="@+id/idLL"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idIVImage"
        android:layout_centerHorizontal="true"
        android:layout_margin="10dp"
        android:orientation="horizontal"
        android:weightSum="2">

        <!--first button for our first image-->
        <Button
            android:id="@+id/idBtnChangeImg"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_margin="10dp"
            android:layout_weight="1"
            android:text="Image 1"
            android:textAllCaps="false" />

        <!--second button for our second image-->
        <Button
            android:id="@+id/idBtnChangeImg2"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_margin="10dp"
            android:layout_weight="1"
            android:text="Image 2"
            android:textAllCaps="false" />
    </LinearLayout>

    <!--sample text view for heading-->
    <TextView
        android:id="@+id/idTVGFG"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idLL"
        android:layout_margin="4dp"
        android:padding="4dp"
        android:text="Welcome to Geeks for Geeks"
        android:textAlignment="center"
        android:textSize="25sp" />

    <!--sample text view for second heading-->
    <TextView
        android:id="@+id/idTVHead"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idTVGFG"
        android:layout_margin="3dp"
        android:padding="4dp"
        android:text="Geeks For Geeks Carnival"
        android:textAlignment="center" />

</RelativeLayout>
```

> **注意**:ImageView 中使用的图像存在于可绘制文件夹中。你可以加上你的。

**第四步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.graphics.Bitmap;
import android.graphics.BitmapFactory;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.ImageView;
import android.widget.RelativeLayout;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;
import androidx.palette.graphics.Palette;

public class MainActivity extends AppCompatActivity {

    // creating variables for our UI components..
    private TextView headTV, gfgTV;
    private ImageView gfgIV;
    private Button changeBtn, changeBtn2;
    private RelativeLayout backRL;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initializing all our variables with their ids.
        headTV = findViewById(R.id.idTVHead);
        gfgTV = findViewById(R.id.idTVGFG);
        gfgIV = findViewById(R.id.idIVImage);
        backRL = findViewById(R.id.idRLBack);
        changeBtn = findViewById(R.id.idBtnChangeImg);
        changeBtn2 = findViewById(R.id.idBtnChangeImg2);

        // on below line we are decoding our image from image resource.
        Bitmap bitmap1 = BitmapFactory.decodeResource(getResources(), R.drawable.logo1);
        Bitmap bitmap2 = BitmapFactory.decodeResource(getResources(), R.drawable.logo2);

        // Get bitmap from drawable resources
        // on below line we are calling a method
        // to change the layout color according to first image.
        createPaletteAsync(bitmap1);

        // on below line we are setting 
        // bitmap to our image view.
        gfgIV.setImageBitmap(bitmap1);

        // on below line we are adding click listener to our button1.
        changeBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                // inside on click we are calling a second method 
                // to change our layout colors with second image bitmaps. .
                createDarkPaletteAsync(bitmap2);

                // on below line we are setting bitmap to our image view.
                gfgIV.setImageBitmap(bitmap2);
            }
        });

        // adding on click listener for our second button.
        changeBtn2.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                // on below line we are calling a method to change
                // our layout colors and we are passing our first image bitmap.
                createPaletteAsync(bitmap1);

                // on below line we are setting 
                // the bitmap to our image view.
                gfgIV.setImageBitmap(bitmap1);
            }
        });
    }

    public void createDarkPaletteAsync(Bitmap bitmap) {

        // on below line we are calling a palette 
        // method from bitmap to get colors from our image.
        Palette.from(bitmap).generate(new Palette.PaletteAsyncListener() {
            public void onGenerated(Palette p) {

                // Use generated instance
                // on below line we are passing
                // a default value to it.
                int defaultValue = 0x000000;

                // on below line we are adding colors to our different views.
                headTV.setTextColor(p.getLightVibrantColor(defaultValue));
                gfgTV.setTextColor(p.getLightVibrantColor(defaultValue));
                backRL.setBackgroundColor(p.getDarkVibrantColor(defaultValue));
                changeBtn.setTextColor(p.getDarkVibrantColor(defaultValue));
                changeBtn.setBackgroundColor(p.getLightVibrantColor(defaultValue));
                changeBtn2.setTextColor(p.getDarkVibrantColor(defaultValue));
                changeBtn2.setBackgroundColor(p.getLightVibrantColor(defaultValue));
            }
        });
    }

    public void createPaletteAsync(Bitmap bitmap) {
        // on below line we are calling a palette method
        // from bitmap to get colors from our image.
        Palette.from(bitmap).generate(new Palette.PaletteAsyncListener() {
            public void onGenerated(Palette p) {

                // Use generated instance
                // on below line we are passing
                // a default value to it.
                int defaultValue = 0x000000;

                // on below line we are adding colors to our different views.
                headTV.setTextColor(p.getDarkVibrantColor(defaultValue));
                gfgTV.setTextColor(p.getDominantColor(defaultValue));
                backRL.setBackgroundColor(p.getLightVibrantColor(defaultValue));
                changeBtn.setTextColor(p.getLightMutedColor(defaultValue));
                changeBtn.setBackgroundColor(p.getDarkVibrantColor(defaultValue));
                changeBtn2.setTextColor(p.getLightMutedColor(defaultValue));
                changeBtn2.setBackgroundColor(p.getDarkVibrantColor(defaultValue));

            }
        });
    }
}
```

现在运行您的应用程序，并查看应用程序的输出。

**输出:**

<video class="wp-video-shortcode" id="video-591537-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210408143913/20210408_143820.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210408143913/20210408_143820.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210408143913/20210408_143820.mp4)</video>