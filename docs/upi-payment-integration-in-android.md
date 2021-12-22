# 安卓 UPI 支付集成

> 原文:[https://www . geeksforgeeks . org/UPI-支付-安卓整合/](https://www.geeksforgeeks.org/upi-payment-integration-in-android/)

如果你在你的安卓应用中销售任何产品或提供任何服务，那么你应该在你的安卓应用中集成一个功能，允许用户通过你的应用进行支付。在本文中，我们将看一下支付网关集成在 Android 中的实现。在本文中，我们将使用轻松合众国际社支付网关库来添加这项功能。

### 我们将在本文中构建什么？

我们将创建一个简单的应用程序，其中我们将显示多个编辑文本字段，我们将允许用户输入付款的详细信息。点击支付按钮后，我们将向用户显示一个对话框，通过安装在用户设备中的不同应用程序进行支付。下面是视频，我们将在其中看到我们将在本文中构建的内容。

<video class="wp-video-shortcode" id="video-578803-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210319155116/1616149095422.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210319155116/1616149095422.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210319155116/1616149095422.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在安卓中添加轻松支付网关的依赖**

导航到**应用程序>渐变脚本> build.gradle(:应用程序)**，并在依赖项部分添加以下依赖项。

> 实现' com . shreyaspatil:EasyUpiPayment:2.0 '

添加此依赖项后，现在同步您的项目，现在我们将继续添加互联网权限。

**第三步:在 AndroidManifest.xml 中添加互联网权限**

导航到**应用程序> AndroidManifest.xml** 并添加下面的代码。

## 可扩展标记语言

```java
<uses-permission android:name="android.permission.INTERNET" />
```

**第 4 步:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <!--edit text for entering amount to be paid-->
    <EditText
        android:id="@+id/idEdtAmount"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginTop="15dp"
        android:layout_marginEnd="8dp"
        android:hint="Enter Amount to be paid"
        android:inputType="numberDecimal" />

    <!--edit text for entering the upi id
        to which we have to make payment-->
    <EditText
        android:id="@+id/idEdtUpi"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idEdtAmount"
        android:layout_marginStart="8dp"
        android:layout_marginTop="15dp"
        android:layout_marginEnd="8dp"
        android:hint="Enter your UPI Id"
        android:inputType="text" />

    <!--edit text for adding the name of the
        user whom we have to make payment-->
    <EditText
        android:id="@+id/idEdtName"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idEdtUpi"
        android:layout_marginStart="8dp"
        android:layout_marginTop="15dp"
        android:layout_marginEnd="8dp"
        android:hint="Enter your Name"
        android:inputType="text" />

    <!--edit text for adding the description for
        the payment which we are making-->
    <EditText
        android:id="@+id/idEdtDescription"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idEdtName"
        android:layout_marginStart="8dp"
        android:layout_marginTop="15dp"
        android:layout_marginEnd="8dp"
        android:hint="Enter Payment Description"
        android:inputType="text" />

    <!--button for making a payment-->
    <Button
        android:id="@+id/idBtnMakePayment"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idEdtDescription"
        android:layout_margin="12dp"
        android:text="Make Payment"
        android:textAllCaps="false" />

    <!--text view for displaying transaction status-->
    <TextView
        android:id="@+id/idTVTransactionDetails"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idBtnMakePayment"
        android:layout_marginTop="30dp"
        android:text="Transaction Details"
        android:textAlignment="center"
        android:textColor="@color/purple_700"
        android:visibility="gone" />

</RelativeLayout>
```

**第五步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.os.Bundle;
import android.text.TextUtils;
import android.util.Log;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

import com.shreyaspatil.EasyUpiPayment.EasyUpiPayment;
import com.shreyaspatil.EasyUpiPayment.listener.PaymentStatusListener;
import com.shreyaspatil.EasyUpiPayment.model.TransactionDetails;

import java.text.SimpleDateFormat;
import java.util.Calendar;
import java.util.Date;
import java.util.Locale;

public class MainActivity extends AppCompatActivity implements PaymentStatusListener {

    // initializing variables for our edit text and button.
    private EditText amountEdt, upiEdt, nameEdt, descEdt;
    private TextView transactionDetailsTV;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initializing all our variables.
        amountEdt = findViewById(R.id.idEdtAmount);
        upiEdt = findViewById(R.id.idEdtUpi);
        nameEdt = findViewById(R.id.idEdtName);
        descEdt = findViewById(R.id.idEdtDescription);
        Button makePaymentBtn = findViewById(R.id.idBtnMakePayment);
        transactionDetailsTV = findViewById(R.id.idTVTransactionDetails);

        // on below line we are getting date and then we are setting this date as transaction id.
        Date c = Calendar.getInstance().getTime();
        SimpleDateFormat df = new SimpleDateFormat("ddMMyyyyHHmmss", Locale.getDefault());
        String transcId = df.format(c);

        // on below line we are adding click listener for our payment button.
        makePaymentBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // on below line we are getting data from our edit text.
                String amount = amountEdt.getText().toString();
                String upi = upiEdt.getText().toString();
                String name = nameEdt.getText().toString();
                String desc = descEdt.getText().toString();
                // on below line we are validating our text field.
                if (TextUtils.isEmpty(amount) && TextUtils.isEmpty(upi) && TextUtils.isEmpty(name) && TextUtils.isEmpty(desc)) {
                    Toast.makeText(MainActivity.this, "Please enter all the details..", Toast.LENGTH_SHORT).show();
                } else {
                    // if the edit text is not empty then
                    // we are calling method to make payment.
                    makePayment(amount, upi, name, desc, transcId);
                }
            }
        });
    }

    private void makePayment(String amount, String upi, String name, String desc, String transactionId) {
        // on below line we are calling an easy payment method and passing 
        // all parameters to it such as upi id,name, description and others.
        final EasyUpiPayment easyUpiPayment = new EasyUpiPayment.Builder()
                .with(this)
                // on below line we are adding upi id.
                .setPayeeVpa(upi)
                // on below line we are setting name to which we are making oayment.
                .setPayeeName(name)
                // on below line we are passing transaction id.
                .setTransactionId(transactionId)
                // on below line we are passing transaction ref id.
                .setTransactionRefId(transactionId)
                // on below line we are adding description to payment.
                .setDescription(desc)
                // on below line we are passing amount which is being paid.
                .setAmount(amount)
                // on below line we are calling a build method to build this ui.
                .build();
        // on below line we are calling a start 
        // payment method to start a payment.
        easyUpiPayment.startPayment();
        // on below line we are calling a set payment
        // status listener method to call other payment methods.
        easyUpiPayment.setPaymentStatusListener(this);
    }

    @Override
    public void onTransactionCompleted(TransactionDetails transactionDetails) {
        // on below line we are getting details about transaction when completed.
        String transcDetails = transactionDetails.getStatus().toString() + "\n" + "Transaction ID : " + transactionDetails.getTransactionId();
        transactionDetailsTV.setVisibility(View.VISIBLE);
        // on below line we are setting details to our text view.
        transactionDetailsTV.setText(transcDetails);
    }

    @Override
    public void onTransactionSuccess() {
        // this method is called when transaction is successful and we are displaying a toast message.
        Toast.makeText(this, "Transaction successfully completed..", Toast.LENGTH_SHORT).show();
    }

    @Override
    public void onTransactionSubmitted() {
        // this method is called when transaction is done 
        // but it may be successful or failure.
        Log.e("TAG", "TRANSACTION SUBMIT");
    }

    @Override
    public void onTransactionFailed() {
        // this method is called when transaction is failure.
        Toast.makeText(this, "Failed to complete transaction", Toast.LENGTH_SHORT).show();
    }

    @Override
    public void onTransactionCancelled() {
        // this method is called when transaction is cancelled.
        Toast.makeText(this, "Transaction cancelled..", Toast.LENGTH_SHORT).show();
    }

    @Override
    public void onAppNotFound() {
        // this method is called when the users device is not having any app installed for making payment.
        Toast.makeText(this, "No app found for making transaction..", Toast.LENGTH_SHORT).show();
    }
}
```

现在运行您的应用程序，并查看应用程序的输出。

> **注意**:一定要在真实的设备上运行你的应用，你应该有一个支付的应用。并把金额用小数表示。

**输出:**

<video class="wp-video-shortcode" id="video-578803-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210319155116/1616149095422.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210319155116/1616149095422.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210319155116/1616149095422.mp4)</video>