# 安卓中的微调器，示例

> 原文:[https://www . geesforgeks . org/spinner-in-Android-using-Java-with-example/](https://www.geeksforgeeks.org/spinner-in-android-using-java-with-example/)

[安卓](https://www.geeksforgeeks.org/android-app-development-fundamentals-for-beginners/)微调器是一个类似下拉列表的视图，用于从选项列表中选择一个选项。它提供了一种从项目列表中选择一个项目的简单方法，当我们单击它时，它会显示所有值的下拉列表。安卓微调器的默认值将是当前选择的值，通过使用**适配器**我们可以轻松地将项目绑定到微调器对象。一般来说，我们通过在我们的 Kotlin 文件中使用 [**ArrayAdapter**](https://www.geeksforgeeks.org/arrayadapter-in-android-with-example/) 来用项目列表填充我们的 Spinner 控件。

### 微调器小部件的不同属性

<figure class="table">

| XML 属性 | 描述 |
| --- | --- |
| 安卓:id | 用来指定视图的 id。 |
| 安卓:textAlignment | 用于下拉列表中的文本对齐。 |
| 安卓:背景 | 用于设置视图的背景。 |
| 安卓:填充 | 用于设置视图的填充。 |
| 安卓:可见性 | 用于设置视图的可见性。 |
| 安卓:重力 | 用来指定视图的重力像中心、顶部、底部等 |

</figure>

### 演示微调器的示例

这里有一个显示 GFG 课程列表的[安卓应用程序](https://www.geeksforgeeks.org/android-app-development-fundamentals-for-beginners/)的例子。使用 ArrayAdapter 存储课程列表。创建一个包含微调器的主活动，点击微调器的任何项目，将显示带有该课程名称的吐司。

**创建活动:**将有一个活动，因此主活动有一个 XML 文件。 **activity_main.xml** :第一个活动的 xml 文件由带有微调器小部件的约束布局组成。 下面是活动的 XML 文件的代码:

## XML

```
<?xml version="1.0" encoding="utf-8"?>
<!--Constraint layout which contain Spinner widget-->

<android.support.constraint.ConstraintLayout

    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.geeksforgeeks.Spinner.MainActivity">

    <!--Spinner widget-->
    <Spinner
        android:id="@+id/coursesspinner"
        android:layout_height="50dp"
        android:layout_width="160dp"
        android:layout_marginEnd="10dp"
        android:layout_marginStart="10dp"   
        android:layout_marginBottom="10dp"
        android:layout_marginTop="10dp"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"/>

</android.support.constraint.ConstraintLayout>
```