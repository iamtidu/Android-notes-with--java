# ANDRIOD

## XML

## Layot
```xml
<?xml version="1.0" encoding="utf-8"?>

<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center_horizontal"
    android:orientation="vertical"
    tools:context=".MainActivity">


    <androidx.appcompat.widget.AppCompatImageView
        android:layout_width="200dp"
        android:layout_height="200dp"
        android:contentDescription="@string/about"
        android:scaleType="fitXY"
        android:src="@drawable/contact" />

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="30dp"
        android:text="@string/about"
        android:textSize="20sp" />

    <EditText
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:ems="12"
        android:hint="Enter date"
        android:inputType="datetime" />

    <androidx.appcompat.widget.AppCompatButton
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Button"

        />
</LinearLayout>
```
INdent passing

```java

package com.example.firstapp;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowInsetsCompat;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Button btnnext ;
        btnnext = findViewById(R.id.btn);

        Intent iNext = new Intent(MainActivity.this, SecondActivity.class);

        btnnext.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                startActivity(iNext); // ye use kare ge jaha woha se hi call hoga

            }
        });

    }
}
```

Bunddel Passing

```java
//mainfile.java
 Intent iNext = new Intent(MainActivity.this, SecondActivity.class);
        iNext.putExtra("title", "Home");
        iNext.putExtra("StudentName", "UDIT");
        iNext.putExtra("Roll_No", 1);  // Pass Roll_No as an integer
```
```java

//secodfile.java

  Intent fromAct = getIntent();
        String title = fromAct.getStringExtra("title");
        String name = fromAct.getStringExtra("StudentName");
        int rollNo = fromAct.getIntExtra("Roll_No", 0);  // Retrieve Roll_No as an integer

        // Find the TextView and set its text
        TextView textStudent = findViewById(R.id.textStudent);
        textStudent.setText("Roll no: " + rollNo + " Name: " + name);
```

splash screen

```java
// splash.java
package com.example.firstapp;

import android.content.Intent;
import android.os.Bundle;
import android.os.Handler;

import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowInsetsCompat;

public class SplashActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        EdgeToEdge.enable(this);
        setContentView(R.layout.activity_splash);

        new Handler().postDelayed(new Runnable() {
            @Override
            public void run() {
                Intent Ihome = new Intent(SplashActivity.this,MainActivity.class);
                startActivity(Ihome);
                finish();

            }
        },4000);

    }
}

```

```xml

<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">

    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.FirstApp"
        tools:targetApi="31">
        <activity android:name=".SplashActivity" android:exported="true">

            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
            </activity>

        <activity
            android:name=".MainActivity">

        </activity>
    </application>

</manifest>

```
Bingo!!
