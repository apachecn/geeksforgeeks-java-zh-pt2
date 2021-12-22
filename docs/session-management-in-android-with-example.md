# 安卓中的会话管理示例

> 原文:[https://www . geesforgeks . org/session-management-in-Android-with-example/](https://www.geeksforgeeks.org/session-management-in-android-with-example/)

当你在安卓中集成登录功能时，会话管理是安卓应用中最重要的功能之一。在你的安卓应用中，如果你使用的是登录功能，那么如果用户第一次登录，你应该保存状态。然后，当用户关闭他的应用程序并重新打开它时，他应该重定向到我们的主屏幕，而不是打开登录屏幕。因此，在本文中，我们将在我们的安卓应用程序中实现会话管理功能。为了实现这个功能，我们创建了一个简单的登录表单和一个主屏幕。在我们的登录表单中，用户必须输入他的凭据并登录应用程序。登录后，用户的凭据将保存在应用程序中，每当他重新打开应用程序时，用户将被重定向到主屏幕。对于我们应用程序内部的会话管理，我们将使用[共享首选项](https://www.geeksforgeeks.org/shared-preferences-in-android-with-examples/)来存储用户凭据。现在我们将进入实现部分。

## 例子

我们将创建一个简单的登录应用程序，如上所述，用于存储用户会话。下面给出了一个示例 GIF，在其中我们将看到我们将在我们的应用程序中构建什么。注意，我们将使用 **Java** 语言来实现这个项目。

![Session Management in Android sample GIF](img/7c56be3c611338b11934d0f3e0c333e0.png)

### 逐步实施

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在字符串. xml 文件**中添加以下字符串

导航至**应用程序>RES>values>strings . XML**并添加以下字符串。

## 可扩展标记语言

```java
<resources>
    <!--app name-->
    <string name="app_name">Session Management</string>
    <!--string for login button-->
    <string name="login">Login</string>
    <!--string for edittext hint in password-->
    <string name="enter_password">Enter password</string>
    <!--string for edittext hint in email-->
    <string name="enter_youe_email">Enter your Email</string>
    <!--string for logout button-->
    <string name="logout">Logout</string>
</resources>
```

**步骤 3:使用 activity_main.xml 文件**

转到 **activity_main.xml** 文件，参考以下代码。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--EditText for getting user email address-->
    <!--input type is set to email-->
    <EditText
        android:id="@+id/idEdtEmail"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="50dp"
        android:layout_marginEnd="10dp"
        android:hint="@string/enter_youe_email"
        android:importantForAutofill="no"
        android:inputType="textEmailAddress" />

    <!--EditText for getting user password-->
    <!--input type is set to password-->
    <EditText
        android:id="@+id/idEdtPassword"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idEdtEmail"
        android:layout_marginStart="10dp"
        android:layout_marginTop="30dp"
        android:layout_marginEnd="10dp"
        android:hint="@string/enter_password"
        android:importantForAutofill="no"
        android:inputType="textPassword" />

    <!--button to continue to login-->
    <Button
        android:id="@+id/idBtnLogin"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idEdtPassword"
        android:layout_marginStart="10dp"
        android:layout_marginTop="30dp"
        android:layout_marginEnd="10dp"
        android:text="@string/login" />

</RelativeLayout>
```

**第 4 步:为主屏幕创建新活动**

导航到**应用程序> java >你的应用程序的包名>右键单击你的包名并新建>活动>清空活动**并确保保持你的语言为 java。将活动命名为**家庭活动。**

**步骤 5:使用 MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.content.Context;
import android.content.Intent;
import android.content.SharedPreferences;
import android.os.Bundle;
import android.text.TextUtils;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    // creating constant keys for shared preferences.
    public static final String SHARED_PREFS = "shared_prefs";

    // key for storing email.
    public static final String EMAIL_KEY = "email_key";

    // key for storing password.
    public static final String PASSWORD_KEY = "password_key";

    // variable for shared preferences.
    SharedPreferences sharedpreferences;
    String email, password;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Initializing EditTexts and our Button
        EditText emailEdt = findViewById(R.id.idEdtEmail);
        EditText passwordEdt = findViewById(R.id.idEdtPassword);
        Button loginBtn = findViewById(R.id.idBtnLogin);

        // getting the data which is stored in shared preferences.
        sharedpreferences = getSharedPreferences(SHARED_PREFS, Context.MODE_PRIVATE);

        // in shared prefs inside het string method
        // we are passing key value as EMAIL_KEY and 
        // default value is
        // set to null if not present.
        email = sharedpreferences.getString(EMAIL_KEY, null);
        password = sharedpreferences.getString(PASSWORD_KEY, null);

        // calling on click listener for login button.
        loginBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // to check if the user fields are empty or not.
                if (TextUtils.isEmpty(emailEdt.getText().toString()) && TextUtils.isEmpty(passwordEdt.getText().toString())) {
                    // this method will call when email and password fields are empty.
                    Toast.makeText(MainActivity.this, "Please Enter Email and Password", Toast.LENGTH_SHORT).show();
                } else {
                    SharedPreferences.Editor editor = sharedpreferences.edit();

                    // below two lines will put values for 
                    // email and password in shared preferences.
                    editor.putString(EMAIL_KEY, emailEdt.getText().toString());
                    editor.putString(PASSWORD_KEY, passwordEdt.getText().toString());

                    // to save our data with key and value.
                    editor.apply();

                    // starting new activity.
                    Intent i = new Intent(MainActivity.this, HomeActivity.class);
                    startActivity(i);
                    finish();
                }
            }
        });
    }

    @Override
    protected void onStart() {
        super.onStart();
        if (email != null && password != null) {
            Intent i = new Intent(MainActivity.this, HomeActivity.class);
            startActivity(i);
        }
    }
}
```

**步骤 6:现在我们将在主屏幕上工作**

在我们的主屏幕中，我们将显示用户的电子邮件地址和注销按钮，以便用户可以注销应用程序。对于主屏幕，我们创建了一个名为“主活动”的活动。导航到**应用程序> res >布局> activity_home.xml** 并将其打开并添加以下代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".HomeActivity">

    <!--Textview for displaying
        user's email address-->
    <TextView
        android:id="@+id/idTVWelcome"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:padding="5dp"
        android:textAlignment="center"
        android:textSize="20sp" />

    <!--button for logging out of the app-->
    <Button
        android:id="@+id/idBtnLogout"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idTVWelcome"
        android:layout_marginStart="20dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="20dp"
        android:text="@string/logout" />

</RelativeLayout>
```

现在我们将转向我们的 HomeActivity 的 java 文件。导航到**应用程序> java >你的应用程序的包名，打开 HomeActivity.java**文件。在该文件中添加以下代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.content.Context;
import android.content.Intent;
import android.content.SharedPreferences;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;

public class HomeActivity extends AppCompatActivity {

    // creating constant keys for shared preferences.
    public static final String SHARED_PREFS = "shared_prefs";

    // key for storing email.
    public static final String EMAIL_KEY = "email_key";

    // key for storing password.
    public static final String PASSWORD_KEY = "password_key";

    // variable for shared preferences.
    SharedPreferences sharedpreferences;
    String email;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_home);

        // initializing our shared preferences.
        sharedpreferences = getSharedPreferences(SHARED_PREFS, Context.MODE_PRIVATE);

        // getting data from shared prefs and 
        // storing it in our string variable.
        email = sharedpreferences.getString(EMAIL_KEY, null);

        // initializing our textview and button.
        TextView welcomeTV = findViewById(R.id.idTVWelcome);
        welcomeTV.setText("Welcome \n" + email);
        Button logoutBtn = findViewById(R.id.idBtnLogout);
        logoutBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                // calling method to edit values in shared prefs.
                SharedPreferences.Editor editor = sharedpreferences.edit();

                // below line will clear 
                // the data in shared prefs.
                editor.clear();

                // below line will apply empty
                // data to shared prefs.
                editor.apply();

                // starting mainactivity after
                // clearing values in shared preferences.
                Intent i = new Intent(HomeActivity.this, MainActivity.class);
                startActivity(i);
                finish();
            }
        });
    }
}
```

### 输出:

<video class="wp-video-shortcode" id="video-530773-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201217123640/Screenrecorder-2020-12-17-12-33-46-364.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201217123640/Screenrecorder-2020-12-17-12-33-46-364.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201217123640/Screenrecorder-2020-12-17-12-33-46-364.mp4)</video>

**出库 github link:**T2【https://github . com/chaitanyamunje/session managendroid】