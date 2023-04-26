## Calculator App

# XML: 

A sample XML code for the layout of the calculator app:

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <EditText
        android:id="@+id/editText1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="32dp"
        android:ems="10"
        android:hint="Enter number 1"
        android:inputType="numberDecimal"
        android:layout_centerHorizontal="true" />

    <EditText
        android:id="@+id/editText2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/editText1"
        android:layout_marginTop="32dp"
        android:ems="10"
        android:hint="Enter number 2"
        android:inputType="numberDecimal"
        android:layout_centerHorizontal="true" />

    <Button
        android:id="@+id/addButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/editText2"
        android:layout_marginTop="32dp"
        android:text="Add"
        android:layout_alignLeft="@+id/editText2"
        android:layout_alignStart="@+id/editText2" />

    <Button
        android:id="@+id/subtractButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/addButton"
        android:layout_marginTop="16dp"
        android:text="Subtract"
        android:layout_alignLeft="@+id/addButton"
        android:layout_alignStart="@+id/addButton" />

    <Button
        android:id="@+id/multiplyButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/subtractButton"
        android:layout_marginTop="16dp"
        android:text="Multiply"
        android:layout_alignLeft="@+id/subtractButton"
        android:layout_alignStart="@+id/subtractButton" />

    <Button
        android:id="@+id/divideButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/multiplyButton"
        android:layout_marginTop="16dp"
        android:text="Divide"
        android:layout_alignLeft="@+id/multiplyButton"
        android:layout_alignStart="@+id/multiplyButton" />

    <TextView
        android:id="@+id/resultTextView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/divideButton"
        android:layout_marginTop="32dp"
        android:text="Result"
        android:layout_centerHorizontal="true" />

</RelativeLayout>
```

In this code, we have defined a `RelativeLayout` as the parent layout, which contains two `EditText` fields for entering two numbers, four `Button` widgets for performing addition, subtraction, multiplication, and division operations, and a `TextView` widget for displaying the result.

# JAVA Code:

A sample code for a simple calculator app in Android:

```
public class MainActivity extends AppCompatActivity {

    private EditText editText1;
    private EditText editText2;
    private Button addButton;
    private Button subtractButton;
    private Button multiplyButton;
    private Button divideButton;
    private TextView resultTextView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editText1 = findViewById(R.id.editText1);
        editText2 = findViewById(R.id.editText2);
        addButton = findViewById(R.id.addButton);
        subtractButton = findViewById(R.id.subtractButton);
        multiplyButton = findViewById(R.id.multiplyButton);
        divideButton = findViewById(R.id.divideButton);
        resultTextView = findViewById(R.id.resultTextView);

        addButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                double num1 = Double.parseDouble(editText1.getText().toString());
                double num2 = Double.parseDouble(editText2.getText().toString());
                double result = num1 + num2;
                resultTextView.setText(String.valueOf(result));
            }
        });

        subtractButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                double num1 = Double.parseDouble(editText1.getText().toString());
                double num2 = Double.parseDouble(editText2.getText().toString());
                double result = num1 - num2;
                resultTextView.setText(String.valueOf(result));
            }
        });

        multiplyButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                double num1 = Double.parseDouble(editText1.getText().toString());
                double num2 = Double.parseDouble(editText2.getText().toString());
                double result = num1 * num2;
                resultTextView.setText(String.valueOf(result));
            }
        });

        divideButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                double num1 = Double.parseDouble(editText1.getText().toString());
                double num2 = Double.parseDouble(editText2.getText().toString());
                if (num2 == 0) {
                    resultTextView.setText("Cannot divide by zero");
                } else {
                    double result = num1 / num2;
                    resultTextView.setText(String.valueOf(result));
                }
            }
        });
    }
}
```

In this code, we have defined an activity named `MainActivity` which contains two `EditText` fields for entering two numbers, four `Button` widgets for performing addition, subtraction, multiplication, and division operations, and a `TextView` widget for displaying the result.

We have set `onClick` listeners for each button, which performs the respective operation based on the input values entered in the `EditText` fields and displays the result in the `TextView` field.

Note that we have also added a check for division by zero to avoid any errors.
