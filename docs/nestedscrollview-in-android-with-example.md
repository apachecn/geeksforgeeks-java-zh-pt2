# 用示例在安卓中嵌套滚动视图

> 原文:[https://www . geeksforgeeks . org/nested crollview-in-Android-with-example/](https://www.geeksforgeeks.org/nestedscrollview-in-android-with-example/)

NestedScrollView 就像 [ScrollView](https://www.geeksforgeeks.org/scrollview-in-android/) 一样，但它支持在新老版本的安卓系统上同时充当嵌套滚动的父级和子级。默认情况下，它处于启用状态。 **嵌套滚动视图**在另一个滚动视图中需要滚动视图时使用。你已经在许多应用程序中看到了这一点，例如当我们打开一个 pdf 文件时，当我们到达 pdf 的末尾时，PDF 文件下方有一个 **Ad** 。这就是**嵌套滚动视图**出现的地方。通常这很难实现，因为系统无法决定滚动哪个视图。我们举个例子来讨论一下安卓中的一个 NestedScrollView。

### 例子

**步骤 1:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。请注意，选择 [Java](https://www.geeksforgeeks.org/java/) 作为语言，尽管我们要用 Java 语言实现这个项目。

**第二步:去编码区之前先做一些前置任务**

*   转到**app->RES->values->**[**strings . XML**](https://www.geeksforgeeks.org/android-res-values-folder/)**并在 **strings.xml** 文件中添加两个随机的 [](http://randomtextgenerator.com/) 文本字符串，以在 **activity_main.xml** 文件中显示这些字符串。**

## **可扩展标记语言**

```java
<resources>
    <string name="app_name">GFG | NestedScrollView </string>
    <string name="random_text_1">
        Hadoop is a data processing tool used to process large size data over distributed
        commodity hardware. The trend of Big Data Hadoop market is on the boom and it’s
          not showing any kind of deceleration in its growth. Today, industries are capable
          of storing all the data generated at their business at an affordable price just
          because of Hadoop. Hadoop helps the industry to know their customer’s behavior,
          customers buying priorities i.e. what they loved the most, and click patterns,
          etc. Hadoop provides personalized recommendations and personalizes ad targeting
          features. Companies are generating thousands of petabytes of data every day so the
          demand for Big Data professionals is very high. Even after a few years,
          Hadoop will be considered as the must-learn skill for the data-scientist
          and Big Data Technology. Companies are investing big in it and it will become
          an in-demand skill in the future. Hadoop provides personalized recommendations
        and personalizes ad targeting
          features. Companies are generating thousands of petabytes of data every day so the
          demand for Big Data professionals is very high. Even after a few years,
          Hadoop will be considered as the must-learn skill for the data-scientist
          and Big Data Technology. Companies are investing big in it and it will become
          an in-demand skill in the future.
    </string>
    <string name="random_text_2">
          Humans are coming closer to the internet at a very fast rate. It means that the
          volume of data Industries is gathering will increase as time passes because of
          more users. Industry’s are gradually analyzing the need for this useful information
          they are getting from their users. It is for sure that the data always tends to
          an increasing pattern so the company’s are eventually acquiring professionals
          skilled with Big Data Technologies. According to NASSCOM, India’s Big Data
          Market will reach 16 billion USD by 2025 from 2 billion USD. The growth of smart
          devices in India is growing at a very huge rate that will cause growth in the
          Big Data Market. Since Big Data is growing the demand for Big Data professionals
          will be high.  Hadoop provides personalized recommendations and personalizes ad targeting
          features. Companies are generating thousands of petabytes of data every day so the
          demand for Big Data professionals is very high. Even after a few years,
          Hadoop will be considered as the must-learn skill for the data-scientist
          and Big Data Technology. Companies are investing big in it and it will become
          an in-demand skill in the future.
    </string>

</resources>
```

****第三步:设计 UI****

**在 **activity_main.xml** 文件中添加**嵌套滚动视图**并在**嵌套滚动视图**中添加一个 [**线形布局**](https://www.geeksforgeeks.org/android-linearlayout-in-kotlin/) 并在**线形布局**中添加两个 [**文本视图**](https://www.geeksforgeeks.org/textview-widget-in-android-using-java-with-examples/) 以显示在字符串. xml 文件中创建的字符串和一个 [**按钮**](https://www.geeksforgeeks.org/button-in-kotlin/)**T23下面是 **activity_main.xml** 文件的代码。您可以在嵌套的滚动视图的线性布局中添加任意多的视图****

## **可扩展标记语言**

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!-- Nested Scroll view -->
    <androidx.core.widget.NestedScrollView
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

        <!-- Linear layout to contain 2 text view and button -->
        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="vertical">

            <!-- showing random text 1 from strings.xml file -->
            <TextView
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:text="@string/random_text_1" />

            <!-- simple button -->
            <Button
                android:layout_width="match_parent"
                android:layout_height="160dp"
                android:background="@color/colorPrimary"
                android:text="Nested Scroll View "
                android:textColor="#ffffff"
                android:textSize="32dp" />

            <!-- showing random text 2 from strings.xml file -->
            <TextView
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:text="@string/random_text_2" />

        </LinearLayout>

    </androidx.core.widget.NestedScrollView>

</RelativeLayout>
```

****第四步:使用 MainActivity.java 文件****

**与**MainActivity.java**文件无关，保持原样。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
}
```

### ****输出:在仿真器上运行****

**<video class="wp-video-shortcode" id="video-485072-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200917114446/nested-scroll-view.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200917114446/nested-scroll-view.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200917114446/nested-scroll-view.mp4)</video>**

****资源:****

*   **从 [Github](https://github.com/olyklohan/Nested-Scroll-View-Android-studio-) 下载完整项目**
*   **下载 [Apk](https://github.com/olyklohan/Nested-Scroll-View-Android-studio-/blob/master/nested%20scroll%20view%20android%20studio.apk) 文件**