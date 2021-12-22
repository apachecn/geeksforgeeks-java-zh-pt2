# 用户使用 Back4App 在安卓系统注册

> 原文:[https://www . geesforgeks . org/user-registration-in-Android-use-back 4 app/](https://www.geeksforgeeks.org/user-registration-in-android-using-back4app/)

**先决条件:** [如何连接安卓 App 和 Back4App？](https://www.geeksforgeeks.org/how-to-connect-android-app-with-back4app/)

我们已经看到在我们的安卓应用中添加了 Back4App。在本文中，我们将了解如何在安卓应用程序中添加用户注册表单，以便用户可以在应用程序中注册自己。

### **本文我们要构建什么？**

我们将构建一个简单的应用程序，其中我们将添加一个简单的用户注册表单，以便用户可以用他们的用户名和密码注册自己。下面是视频，我们将在其中看到我们将在本文中构建的内容。

<video class="wp-video-shortcode" id="video-571071-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210307160704/Screenrecorder-2021-03-07-16-05-43-370.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210307160704/Screenrecorder-2021-03-07-16-05-43-370.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210307160704/Screenrecorder-2021-03-07-16-05-43-370.mp4)</video>

### **分步实施**

本文是**如何连接安卓 App 和 Back4App 的续篇。**

**步骤 1:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--text view for heading-->
    <TextView
        android:id="@+id/idTVHeader"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="30dp"
        android:gravity="center_horizontal"
        android:padding="5dp"
        android:text="Welcome to Geeks for Geeks \n Register Form"
        android:textAlignment="center"
        android:textColor="@color/purple_700"
        android:textSize="18sp" />

    <!--edit text for user name-->
    <EditText
        android:id="@+id/idEdtUserName"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idTVHeader"
        android:layout_marginStart="10dp"
        android:layout_marginTop="50dp"
        android:layout_marginEnd="10dp"
        android:hint="Enter UserName"
        android:inputType="textEmailAddress" />

    <!--edit text for user password-->
    <EditText
        android:id="@+id/idEdtPassword"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idEdtUserName"
        android:layout_marginStart="10dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="10dp"
        android:hint="Enter Password"
        android:inputType="textPassword" />

    <!--button to register our new user-->
    <Button
        android:id="@+id/idBtnRegister"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idEdtPassword"
        android:layout_marginStart="10dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="10dp"
        android:text="Register User"
        android:textAllCaps="false" />

</RelativeLayout>
```

**第二步:注册后创建一个新的活动来重定向我们的用户**

导航到**应用程序> java >您的应用程序的包名>右键单击它>新建>空活动**并将其命名为**家庭活动**。或者你也可以参考这篇文章 [**如何在安卓工作室创建新活动？**](https://www.geeksforgeeks.org/how-to-create-constructor-getter-setter-methods-and-new-activity-in-android-studio-using-shortcuts/)

**步骤 3:使用 activity_home.xml 文件**

导航到**应用程序> res >布局> activity_home.xml** 文件，并向其中添加以下代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".HomeActivity">

    <!--text view for displaying heading-->
    <TextView
        android:id="@+id/idTVHeader"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:gravity="center_horizontal"
        android:text="Welcome to Geeks for Geeks"
        android:textAlignment="center"
        android:textColor="@color/purple_700"
        android:textSize="18sp" />

    <!--text view for displaying user name-->
    <TextView
        android:id="@+id/idTVUserName"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idTVHeader"
        android:layout_centerInParent="true"
        android:layout_marginTop="20dp"
        android:gravity="center_horizontal"
        android:text="UserName"
        android:textAlignment="center"
        android:textColor="@color/purple_700"
        android:textSize="25sp" />

</RelativeLayout>
```