# Ex.No:3a Develop program to create a text field and a button “Navigate”. When you enter “www.gmail.com” and press navigate button it should open google page using Implicit Intents.


## AIM:

To create a navigate button using Implicit Intent to display the gmail page using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:



## PROGRAM:
```
/*
Program to print the text “Implicitintent”.
Developed by:
Registeration Number :
*/
```
## Activity_main.xml

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#5B647A"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/editText"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:backgroundTint="#2196F3"
        android:textSize="20sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.278" />

    <Button
        android:id="@+id/btn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:backgroundTint="#59C354"
        android:backgroundTintMode="add"
        android:onClick="search"
        android:text="Search"
        android:textColor="#F44336"
        app:icon="@color/design_default_color_error"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/editText"
        app:rippleColor="#A12FB4" />


</androidx.constraintlayout.widget.ConstraintLayout>
```
## MainActivity.java
```

package com.example.implicitintent;

import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

    EditText editText;
    Button button;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editText = findViewById(R.id.editText);
        button = findViewById(R.id.btn);

        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

                String url = editText.getText().toString().trim();

                if (url.isEmpty()) {
                    editText.setError("Enter a website URL");
                    return;
                }

                if (!url.startsWith("http://") &&
                        !url.startsWith("https://")) {
                    url = "https://" + url;
                }

                try {
                    Intent intent = new Intent(
                            Intent.ACTION_VIEW,
                            Uri.parse(url)
                    );
                    startActivity(intent);
                } catch (Exception e) {
                    Toast.makeText(
                            MainActivity.this,
                            "Unable to open website",
                            Toast.LENGTH_SHORT
                    ).show();
                }
            }
        });
    }
}


```
## OUTPUT
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/841246d8-a305-4c02-b04a-e02cc0faa140" />
<img width="1336" height="1031" alt="Screenshot 2026-10-24 132958" src="https://github.com/user-attachments/assets/6562d916-9403-462e-80c7-fbfe27d93f81" />



## RESULT
Thus a Simple Android Application create a navigate button using Implicit Intent to display the gmail page using Android Studio is developed and executed successfully.


