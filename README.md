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
