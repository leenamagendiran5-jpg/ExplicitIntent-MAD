# Ex.No: 2b To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## AIM:

To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

Step 1: Start the application and create two activities.
Step 2: Get a number from the user using EditText.
Step 3: Create an Explicit Intent and pass the number to the second activity.
Step 4: Calculate the factorial of the number using a for loop.
Step 5: Display the factorial result in the second screen using TextView.


## PROGRAM:
```
/*
Program to print the text “ExplicitIntent”.
Developed by: Leena Shree M 
Registeration Number : 212225220056
*/
```
## MainActivity.java
```
package com.example.explicitlntent;

import android.content.Intent;
import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText number;
    Button factorial;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        number = findViewById(R.id.number);
        factorial = findViewById(R.id.factorial);

        factorial.setOnClickListener(v -> {

            String num = number.getText().toString();

            if (num.isEmpty()) {
                Toast.makeText(this, "Enter a number", Toast.LENGTH_SHORT).show();
            } else {
                Intent intent = new Intent(MainActivity.this, SecondActivity.class);
                intent.putExtra("number", Integer.parseInt(num));
                startActivity(intent);
            }
        });
    }
}
```
## activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="20dp">

    <EditText
        android:id="@+id/number"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter a number"
        android:inputType="number" />

    <Button
        android:id="@+id/factorial"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Factorial" />

</LinearLayout>
```
## SecondActivity.java
```
package com.example.explicitlntent;

import android.os.Bundle;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;

public class SecondActivity extends AppCompatActivity {

    TextView result;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_second);

        result = findViewById(R.id.result);

        int num = getIntent().getIntExtra("number", 0);

        long fact = 1;

        for (int i = 1; i <= num; i++) {
            fact = fact * i;
        }

        result.setText("Factorial of " + num + " = " + fact);
    }
}
```
## activity_second.xml
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="20dp">

    <TextView
        android:id="@+id/result"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textSize="24sp"
        android:textStyle="bold" />

</LinearLayout>
```
## OUTPUT

<img width="1916" height="1021" alt="Screenshot 2026-11-03 091235" src="https://github.com/user-attachments/assets/7299e832-f85e-4bdd-9746-a3401a9645ba" />

<img width="1917" height="1018" alt="Screenshot 2026-11-03 091305" src="https://github.com/user-attachments/assets/6ba98b44-58a2-4599-9d7e-3bdd4e30cfcb" />

<img width="1917" height="1020" alt="Screenshot 2026-11-03 091324" src="https://github.com/user-attachments/assets/fec37ae4-5b46-46b4-a80c-fdf05b3639ad" />


## RESULT
Thus a Simple Android Application create a Explicit Intents using Android Studio is developed and executed successfully.


