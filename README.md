
# Ex.No:3 Design an android application Send SMS using Intent.


## AIM:

To create and design an android application Send SMS using Intent using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as smsintent and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Send SMS and Display details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```

Program to create and design an android application Send SMS using Intent.
Developed by:
Registeration Number :

```
### mainActivity.java
```
package com.example.smsapp;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.telephony.SmsManager;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity
{

    EditText phoneNumberInput, messageInput;
    Button sendButton;

    @Override
    protected void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        phoneNumberInput = findViewById(R.id.phone_number_input);
        messageInput = findViewById(R.id.message_input);
        sendButton = findViewById(R.id.send_button);

        sendButton.setOnClickListener(new View.OnClickListener()
        {
            @Override
            public void onClick(View v)
            {
                sendSMS();
            }
        });
    }

    private void sendSMS()
    {
        String phoneNumber = phoneNumberInput.getText().toString();
        String message = messageInput.getText().toString();

        if (phoneNumber.isEmpty() || message.isEmpty())
        {
            Toast.makeText(this, "Please enter a phone number and a message.", Toast.LENGTH_SHORT).show();
            return;
        }

        try
        {

            SmsManager smsManager = SmsManager.getDefault();
            smsManager.sendTextMessage(phoneNumber, null, message, null, null);
            Toast.makeText(this, "SMS sent successfully!", Toast.LENGTH_SHORT).show();
        }
        catch (Exception e)
        {
            Toast.makeText(this, "Failed to send SMS. Make sure you have the SEND_SMS permission enabled.", Toast.LENGTH_LONG).show();
            e.printStackTrace();
        }
    }
}

```
### activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp"
    android:gravity="center"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="294dp"
        android:layout_height="140dp"
        android:layout_marginBottom="32dp"
        android:text="Simple SMS Sender"
        android:textSize="24sp"
        android:textStyle="bold" />

    <EditText
        android:id="@+id/phone_number_input"
        android:layout_width="337dp"
        android:layout_height="69dp"
        android:focusable="auto"
        android:hint="Enter phone number"
        android:inputType="phone" />

    <EditText
        android:id="@+id/message_input"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:gravity="top"
        android:hint="Enter your message"
        android:inputType="textMultiLine"
        android:minLines="3"
        android:padding="12dp" />

    <Button
        android:id="@+id/send_button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Send SMS"
        android:layout_marginTop="24dp" />

</LinearLayout>

```
### AndroidManifist.xml
```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    package="com.example.smsapp">

    <uses-permission android:name="android.permission.SEND_SMS" />
    <uses-feature
        android:name="android.hardware.telephony"
        android:required="false" />

    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.SmsApp"
        tools:ignore="ExtraText">
        <activity
            android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>
</manifest>

```
## OUTPUT
### activity_main.xml
<img width="1920" height="1080" alt="Screenshot 2025-09-27 213055" src="https://github.com/user-attachments/assets/1fe5429d-b06e-4881-83d4-d48ad0f1b3dd" /><br>
### MainActivity.java
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/58823da5-fa75-454c-afed-2ae4d4d6cb23" /><br>
### AndroidManifist.xml
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/64dd9f7a-17fb-466e-b55c-1a3179ce2aa0" /><br>
### SmsApp
<img width="365" height="835" alt="Screenshot 2025-09-28 164008" src="https://github.com/user-attachments/assets/8c926d78-3ef0-47e3-a9be-bf1d45b0e6ce" />  <img width="376" height="837" alt="Screenshot 2025-09-28 163516" src="https://github.com/user-attachments/assets/aab6494e-8371-4bd0-81c1-db2dbbb5ec78" />



## RESULT
Thus a Simple Android Application create and design an android application Send SMS using Intent using Android Studio is developed and executed successfully.
