# 用户使用 Back4App 登录安卓

> 原文:[https://www . geesforgeks . org/user-log in-in-Android-using-back 4 app/](https://www.geeksforgeeks.org/user-login-in-android-using-back4app/)

我们已经看到使用 Back4App 在安卓中实现[用户注册。在那篇文章中，我们已经在我们的应用程序中实现了用户注册。在本文中，我们将看看用户登录在我们的安卓应用程序中的实现。](https://www.geeksforgeeks.org/user-registration-in-android-using-back4app/)

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将在安卓应用程序中显示一个用户登录表单，使用这个登录表单，我们将允许我们的用户在我们的应用程序中登录。下面给出了一个示例视频，让我们了解一下在本文中要做什么。请注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-571115-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210307170356/Screenrecorder-2021-03-07-17-01-12-220.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210307170356/Screenrecorder-2021-03-07-17-01-12-220.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210307170356/Screenrecorder-2021-03-07-17-01-12-220.mp4)</video>

### **分步实施**

本文是**用户使用 Back4App** 在安卓系统注册的续篇。

**步骤 1:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
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
        android:text="Welcome to Geeks for Geeks \n Login Form"
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
        android:id="@+id/idBtnLogin"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idEdtPassword"
        android:layout_marginStart="10dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="10dp"
        android:text="Login"
        android:textAllCaps="false" />

</RelativeLayout>
```

**第二步:注册后创建一个新的活动来重定向我们的用户**

导航到**应用程序> java >您的应用程序的包名>右键单击它>新建>空活动**并将其命名为**家庭活动**。或者你也可以参考这篇文章 [**如何在安卓工作室创建新活动？**](https://www.geeksforgeeks.org/how-to-create-constructor-getter-setter-methods-and-new-activity-in-android-studio-using-shortcuts/)

**步骤 3:使用 activity_home.xml 文件**

导航到**应用程序> res >布局> activity_home.xml** 文件，并向其中添加以下代码。

## 可扩展标记语言

```
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
        android:text="Welcome back again to Geeks for Geeks"
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

    <!--button for making user log out-->
    <Button
        android:id="@+id/idBtnLogout"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/idTVUserName"
        android:layout_centerInParent="true"
        android:layout_marginTop="10dp"
        android:text="LogOut"
        android:textAllCaps="false" />

</RelativeLayout>
```

**第四步:处理 HomeActivity.java 文件**

导航到**应用程序> java >你的应用程序的包名>HomeActivity.java**文件，并添加下面的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

import com.parse.ParseUser;

public class HomeActivity extends AppCompatActivity {

    // creating a variable
    // for our text view..
    private TextView userNameTV;

    // button for logout
    private Button logoutBtn;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_home);
        logoutBtn = findViewById(R.id.idBtnLogout);

        // initializing our variables
        userNameTV = findViewById(R.id.idTVUserName);

        // getting data from intent.
        String name = getIntent().getStringExtra("username");

        // setting data to our text view.
        userNameTV.setText(name);

        // initializing click listener for logout button
        logoutBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // calling a method to logout our user.
                ParseUser.logOutInBackground(e -> {
                    if (e == null) {
                        Toast.makeText(HomeActivity.this, "User Logged Out", Toast.LENGTH_SHORT).show();
                        Intent i = new Intent(HomeActivity.this, MainActivity.class);
                        startActivity(i);
                        finish();
                    }
                });
            }
        });
    }
}
```

**第五步:处理****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.Intent;
import android.os.Bundle;
import android.text.TextUtils;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

import com.parse.ParseUser;

public class MainActivity extends AppCompatActivity {

    // creating variables for our edit text and buttons.
    private EditText userNameEdt, passwordEdt;
    private Button loginBtn;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initializing our edit text  and buttons.
        userNameEdt = findViewById(R.id.idEdtUserName);
        passwordEdt = findViewById(R.id.idEdtPassword);
        loginBtn = findViewById(R.id.idBtnLogin);

        // adding on click listener for our button.
        loginBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                // on below line we are getting data from our edit text.
                String userName = userNameEdt.getText().toString();
                String password = passwordEdt.getText().toString();

                // checking if the entered text is empty or not.
                if (TextUtils.isEmpty(userName) && TextUtils.isEmpty(password)) {
                    Toast.makeText(MainActivity.this, "Please enter user name and password", Toast.LENGTH_SHORT).show();
                }

                // calling a method to login our user.
                loginUser(userName, password);
            }
        });
    }

    private void loginUser(String userName, String password) {
        // calling a method to login a user.
        ParseUser.logInInBackground(userName, password, (parseUser, e) -> {
            // after login checking if the user is null or not.
            if (parseUser != null) {
                // if the user is not null then we will display a toast message
                // with user login and passing that user to new activity.
                Toast.makeText(this, "Login Successful ", Toast.LENGTH_SHORT).show();
                Intent i = new Intent(MainActivity.this, HomeActivity.class);
                i.putExtra("username", userName);
                startActivity(i);
            } else {
                // display an toast message when user logout of the app.
                ParseUser.logOut();
                Toast.makeText(MainActivity.this, e.getMessage(), Toast.LENGTH_LONG).show();
            }
        });
    }
}
```

现在运行你的应用，看到应用的输出:

**输出:**

<video class="wp-video-shortcode" id="video-571115-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210307170356/Screenrecorder-2021-03-07-17-01-12-220.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210307170356/Screenrecorder-2021-03-07-17-01-12-220.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210307170356/Screenrecorder-2021-03-07-17-01-12-220.mp4)</video>

**在下方链接查看项目:**[https://github . com/ChaitanyaMunje/GFG-back 4 app/tree/LoginForm](https://github.com/ChaitanyaMunje/GFG-Back4App/tree/LoginForm)