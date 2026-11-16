# Android Practicals – Set A and Set B

- [Set A – 8 Marks, Q1 to Q20](#set-a--android-practical-8-marks)
- [Set B – 12 Marks, Q1 to Q14](#set-b--android-mobile-application-development-12-marks)

---

# Set A – Android Practical (8 Marks)

8 Marks | Questions 1 to 20 | Complete XML and Kotlin solutions

**How to use:** Each question has an XML layout and a Kotlin Activity. Copy the XML into `activity_main.xml` and the Kotlin code into `MainActivity.kt`. Use the copy button at the top right of each code block.

**Important:** In every Kotlin file, change `com.example.myapplication` to the package name at the top of your own `MainActivity.kt`. Do not change XML IDs unless you also change the matching Kotlin IDs.

**Input note:** Questions that accept whole numbers use integer input. Other calculation questions use decimal input.

## Contents

1. [Q.1 – Addition of Two Numbers](#a-q1)
2. [Q.2 – Subtraction of Two Numbers](#a-q2)
3. [Q.3 – Multiplication of Two Numbers](#a-q3)
4. [Q.4 – Division of Two Numbers](#a-q4)
5. [Q.5 – Area of Rectangle](#a-q5)
6. [Q.6 – Area of Square](#a-q6)
7. [Q.7 – Area of Circle](#a-q7)
8. [Q.8 – Square of a Number](#a-q8)
9. [Q.9 – Cube of a Number](#a-q9)
10. [Q.10 – Even or Odd](#a-q10)
11. [Q.11 – Area of Triangle](#a-q11)
12. [Q.12 – Average of Two Numbers](#a-q12)
13. [Q.13 – Celsius to Fahrenheit Conversion](#a-q13)
14. [Q.14 – Positive, Negative or Zero](#a-q14)
15. [Q.15 – Largest of Two Numbers](#a-q15)
16. [Q.16 – Largest of Three Numbers](#a-q16)
17. [Q.17 – Pass or Fail with Marks Validation](#a-q17)
18. [Q.18 – Simple Interest](#a-q18)
19. [Q.19 – Perimeter of Rectangle](#a-q19)
20. [Q.20 – Percentage Calculation](#a-q20)

<a id="a-q1"></a>
## Q.1 – Addition of Two Numbers

Accept two numbers and display their sum when the Add button is clicked.

### 1. XML – activity_main.xml

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/num1"
        android:hint="Enter first number"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <EditText
        android:id="@+id/num2"
        android:hint="Enter second number"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnAdd"
        android:text="Add"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <TextView
        android:id="@+id/txtResult"
        android:textSize="20sp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingTop="12dp" />
</LinearLayout>
```

### 2. Kotlin – MainActivity.kt

```kotlin
package com.example.myapplication

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val button = findViewById<Button>(R.id.btnAdd)
        button.setOnClickListener {
            val num1 = findViewById<EditText>(R.id.num1)
            val num2 = findViewById<EditText>(R.id.num2)
            val result = findViewById<TextView>(R.id.txtResult)

            val a = num1.text.toString().toDouble()
            val b = num2.text.toString().toDouble()

            result.text = "Sum = ${a + b}"
        }
    }
}
```

Sample input: 10, 20  
Expected output: Sum = 30.0

---

<a id="a-q2"></a>
## Q.2 – Subtraction of Two Numbers

Accept two numbers and display their difference when the Subtract button is clicked.

### 1. XML – activity_main.xml

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/num1"
        android:hint="Enter first number"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <EditText
        android:id="@+id/num2"
        android:hint="Enter second number"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnSubtract"
        android:text="Subtract"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <TextView
        android:id="@+id/txtResult"
        android:textSize="20sp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingTop="12dp" />
</LinearLayout>
```

### 2. Kotlin – MainActivity.kt

```kotlin
package com.example.myapplication

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val button = findViewById<Button>(R.id.btnSubtract)
        button.setOnClickListener {
            val num1 = findViewById<EditText>(R.id.num1)
            val num2 = findViewById<EditText>(R.id.num2)
            val result = findViewById<TextView>(R.id.txtResult)

            val a = num1.text.toString().toDouble()
            val b = num2.text.toString().toDouble()

            result.text = "Difference = ${a - b}"
        }
    }
}
```

Sample input: 20, 8  
Expected output: Difference = 12.0

---

<a id="a-q3"></a>
## Q.3 – Multiplication of Two Numbers

Accept two numbers and display their product when the Multiply button is clicked.

### 1. XML – activity_main.xml

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/num1"
        android:hint="Enter first number"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <EditText
        android:id="@+id/num2"
        android:hint="Enter second number"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnMultiply"
        android:text="Multiply"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <TextView
        android:id="@+id/txtResult"
        android:textSize="20sp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingTop="12dp" />
</LinearLayout>
```

### 2. Kotlin – MainActivity.kt

```kotlin
package com.example.myapplication

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val button = findViewById<Button>(R.id.btnMultiply)
        button.setOnClickListener {
            val num1 = findViewById<EditText>(R.id.num1)
            val num2 = findViewById<EditText>(R.id.num2)
            val result = findViewById<TextView>(R.id.txtResult)

            val a = num1.text.toString().toDouble()
            val b = num2.text.toString().toDouble()

            result.text = "Product = ${a * b}"
        }
    }
}
```

Sample input: 5, 4  
Expected output: Product = 20.0

---

<a id="a-q4"></a>
## Q.4 – Division of Two Numbers

Accept two numbers and display their quotient when the Divide button is clicked. Display an appropriate message if the second number is zero.

### 1. XML – activity_main.xml

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/num1"
        android:hint="Enter first number"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <EditText
        android:id="@+id/num2"
        android:hint="Enter second number"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnDivide"
        android:text="Divide"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <TextView
        android:id="@+id/txtResult"
        android:textSize="20sp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingTop="12dp" />
</LinearLayout>
```

### 2. Kotlin – MainActivity.kt

```kotlin
package com.example.myapplication

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val button = findViewById<Button>(R.id.btnDivide)
        button.setOnClickListener {
            val num1 = findViewById<EditText>(R.id.num1)
            val num2 = findViewById<EditText>(R.id.num2)
            val result = findViewById<TextView>(R.id.txtResult)

            val a = num1.text.toString().toDouble()
            val b = num2.text.toString().toDouble()

            if (b == 0.0) {
                result.text = "Cannot divide by zero"
            } else {
                result.text = "Quotient = ${a / b}"
            }
        }
    }
}
```

Sample input: 10, 2  
Expected output: Quotient = 5.0; if second number is 0: Cannot divide by zero

---

<a id="a-q5"></a>
## Q.5 – Area of Rectangle

Accept the length and breadth of a rectangle and calculate its area.

### 1. XML – activity_main.xml

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/length"
        android:hint="Enter length"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <EditText
        android:id="@+id/breadth"
        android:hint="Enter breadth"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnCalculate"
        android:text="Calculate"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <TextView
        android:id="@+id/txtResult"
        android:textSize="20sp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingTop="12dp" />
</LinearLayout>
```

### 2. Kotlin – MainActivity.kt

```kotlin
package com.example.myapplication

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val button = findViewById<Button>(R.id.btnCalculate)
        button.setOnClickListener {
            val length = findViewById<EditText>(R.id.length)
            val breadth = findViewById<EditText>(R.id.breadth)
            val result = findViewById<TextView>(R.id.txtResult)

            val l = length.text.toString().toDouble()
            val b = breadth.text.toString().toDouble()

            val area = l * b
            result.text = "Area = $area"
        }
    }
}
```

Sample input: 5, 3  
Expected output: Area = 15.0

---

<a id="a-q6"></a>
## Q.6 – Area of Square

Accept the side of a square and calculate its area.

### 1. XML – activity_main.xml

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/side"
        android:hint="Enter side"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnCalculate"
        android:text="Calculate"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <TextView
        android:id="@+id/txtResult"
        android:textSize="20sp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingTop="12dp" />
</LinearLayout>
```

### 2. Kotlin – MainActivity.kt

```kotlin
package com.example.myapplication

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val button = findViewById<Button>(R.id.btnCalculate)
        button.setOnClickListener {
            val side = findViewById<EditText>(R.id.side)
            val result = findViewById<TextView>(R.id.txtResult)

            val s = side.text.toString().toDouble()

            val area = s * s
            result.text = "Area = $area"
        }
    }
}
```

Sample input: 4  
Expected output: Area = 16.0

---

<a id="a-q7"></a>
## Q.7 – Area of Circle

Accept the radius of a circle and calculate its area.

### 1. XML – activity_main.xml

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/radius"
        android:hint="Enter radius"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnCalculate"
        android:text="Calculate"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <TextView
        android:id="@+id/txtResult"
        android:textSize="20sp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingTop="12dp" />
</LinearLayout>
```

### 2. Kotlin – MainActivity.kt

```kotlin
package com.example.myapplication

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val button = findViewById<Button>(R.id.btnCalculate)
        button.setOnClickListener {
            val radius = findViewById<EditText>(R.id.radius)
            val result = findViewById<TextView>(R.id.txtResult)

            val r = radius.text.toString().toDouble()

            val area = 3.14 * r * r
            result.text = "Area = $area"
        }
    }
}
```

Sample input: 2  
Expected output: Area = 12.56

Formula: Area of circle = 3.14 × radius × radius.

---

<a id="a-q8"></a>
## Q.8 – Square of a Number

Accept a number and calculate its square.

### 1. XML – activity_main.xml

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/number"
        android:hint="Enter number"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnCalculate"
        android:text="Calculate"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <TextView
        android:id="@+id/txtResult"
        android:textSize="20sp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingTop="12dp" />
</LinearLayout>
```

### 2. Kotlin – MainActivity.kt

```kotlin
package com.example.myapplication

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val button = findViewById<Button>(R.id.btnCalculate)
        button.setOnClickListener {
            val number = findViewById<EditText>(R.id.number)
            val result = findViewById<TextView>(R.id.txtResult)

            val n = number.text.toString().toDouble()

            val square = n * n
            result.text = "Square = $square"
        }
    }
}
```

Sample input: 6  
Expected output: Square = 36.0

---

<a id="a-q9"></a>
## Q.9 – Cube of a Number

Accept a number and calculate its cube.

### 1. XML – activity_main.xml

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/number"
        android:hint="Enter number"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnCalculate"
        android:text="Calculate"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <TextView
        android:id="@+id/txtResult"
        android:textSize="20sp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingTop="12dp" />
</LinearLayout>
```

### 2. Kotlin – MainActivity.kt

```kotlin
package com.example.myapplication

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val button = findViewById<Button>(R.id.btnCalculate)
        button.setOnClickListener {
            val number = findViewById<EditText>(R.id.number)
            val result = findViewById<TextView>(R.id.txtResult)

            val n = number.text.toString().toDouble()

            val cube = n * n * n
            result.text = "Cube = $cube"
        }
    }
}
```

Sample input: 3  
Expected output: Cube = 27.0

---

<a id="a-q10"></a>
## Q.10 – Even or Odd

Accept a number and check whether it is even or odd.

### 1. XML – activity_main.xml

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/number"
        android:hint="Enter an integer"
        android:inputType="number"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnCheck"
        android:text="Check"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <TextView
        android:id="@+id/txtResult"
        android:textSize="20sp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingTop="12dp" />
</LinearLayout>
```

### 2. Kotlin – MainActivity.kt

```kotlin
package com.example.myapplication

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val button = findViewById<Button>(R.id.btnCheck)
        button.setOnClickListener {
            val number = findViewById<EditText>(R.id.number)
            val result = findViewById<TextView>(R.id.txtResult)

            val n = number.text.toString().toInt()

            if (n % 2 == 0) {
                result.text = "Even Number"
            } else {
                result.text = "Odd Number"
            }
        }
    }
}
```

Sample input: 7  
Expected output: Odd Number

---

<a id="a-q11"></a>
## Q.11 – Area of Triangle

Accept the base and height of a triangle and calculate its area.

### 1. XML – activity_main.xml

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/base"
        android:hint="Enter base"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <EditText
        android:id="@+id/height"
        android:hint="Enter height"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnCalculate"
        android:text="Calculate"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <TextView
        android:id="@+id/txtResult"
        android:textSize="20sp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingTop="12dp" />
</LinearLayout>
```

### 2. Kotlin – MainActivity.kt

```kotlin
package com.example.myapplication

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val button = findViewById<Button>(R.id.btnCalculate)
        button.setOnClickListener {
            val base = findViewById<EditText>(R.id.base)
            val height = findViewById<EditText>(R.id.height)
            val result = findViewById<TextView>(R.id.txtResult)

            val b = base.text.toString().toDouble()
            val h = height.text.toString().toDouble()

            val area = (b * h) / 2
            result.text = "Area = $area"
        }
    }
}
```

Sample input: 6, 4  
Expected output: Area = 12.0

---

<a id="a-q12"></a>
## Q.12 – Average of Two Numbers

Accept two numbers and calculate their average.

### 1. XML – activity_main.xml

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/num1"
        android:hint="Enter first number"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <EditText
        android:id="@+id/num2"
        android:hint="Enter second number"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnAverage"
        android:text="Average"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <TextView
        android:id="@+id/txtResult"
        android:textSize="20sp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingTop="12dp" />
</LinearLayout>
```

### 2. Kotlin – MainActivity.kt

```kotlin
package com.example.myapplication

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val button = findViewById<Button>(R.id.btnAverage)
        button.setOnClickListener {
            val num1 = findViewById<EditText>(R.id.num1)
            val num2 = findViewById<EditText>(R.id.num2)
            val result = findViewById<TextView>(R.id.txtResult)

            val a = num1.text.toString().toDouble()
            val b = num2.text.toString().toDouble()

            val average = (a + b) / 2
            result.text = "Average = $average"
        }
    }
}
```

Sample input: 10, 20  
Expected output: Average = 15.0

---

<a id="a-q13"></a>
## Q.13 – Celsius to Fahrenheit Conversion

Accept temperature in Celsius and convert it into Fahrenheit.

### 1. XML – activity_main.xml

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/celsius"
        android:hint="Enter temperature in Celsius"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnConvert"
        android:text="Convert"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <TextView
        android:id="@+id/txtResult"
        android:textSize="20sp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingTop="12dp" />
</LinearLayout>
```

### 2. Kotlin – MainActivity.kt

```kotlin
package com.example.myapplication

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val button = findViewById<Button>(R.id.btnConvert)
        button.setOnClickListener {
            val celsius = findViewById<EditText>(R.id.celsius)
            val result = findViewById<TextView>(R.id.txtResult)

            val c = celsius.text.toString().toDouble()

            val fahrenheit = (c * 9 / 5) + 32
            result.text = "Fahrenheit = $fahrenheit"
        }
    }
}
```

Sample input: 0  
Expected output: Fahrenheit = 32.0

Formula: Fahrenheit = (Celsius × 9/5) + 32.

---

<a id="a-q14"></a>
## Q.14 – Positive, Negative or Zero

Accept a number and check whether it is positive, negative or zero.

### 1. XML – activity_main.xml

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/number"
        android:hint="Enter number"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnCheck"
        android:text="Check"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <TextView
        android:id="@+id/txtResult"
        android:textSize="20sp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingTop="12dp" />
</LinearLayout>
```

### 2. Kotlin – MainActivity.kt

```kotlin
package com.example.myapplication

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val button = findViewById<Button>(R.id.btnCheck)
        button.setOnClickListener {
            val number = findViewById<EditText>(R.id.number)
            val result = findViewById<TextView>(R.id.txtResult)

            val n = number.text.toString().toDouble()

            if (n > 0) {
                result.text = "Positive Number"
            } else if (n < 0) {
                result.text = "Negative Number"
            } else {
                result.text = "Zero"
            }
        }
    }
}
```

Sample input: -5  
Expected output: Negative Number

---

<a id="a-q15"></a>
## Q.15 – Largest of Two Numbers

Accept two numbers and display the largest number.

### 1. XML – activity_main.xml

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/num1"
        android:hint="Enter first number"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <EditText
        android:id="@+id/num2"
        android:hint="Enter second number"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnFind"
        android:text="Find Largest"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <TextView
        android:id="@+id/txtResult"
        android:textSize="20sp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingTop="12dp" />
</LinearLayout>
```

### 2. Kotlin – MainActivity.kt

```kotlin
package com.example.myapplication

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val button = findViewById<Button>(R.id.btnFind)
        button.setOnClickListener {
            val num1 = findViewById<EditText>(R.id.num1)
            val num2 = findViewById<EditText>(R.id.num2)
            val result = findViewById<TextView>(R.id.txtResult)

            val a = num1.text.toString().toDouble()
            val b = num2.text.toString().toDouble()

            if (a > b) {
                result.text = "Largest = $a"
            } else if (b > a) {
                result.text = "Largest = $b"
            } else {
                result.text = "Both numbers are equal"
            }
        }
    }
}
```

Sample input: 12, 8  
Expected output: Largest = 12.0

---

<a id="a-q16"></a>
## Q.16 – Largest of Three Numbers

Accept three numbers and display the largest number.

### 1. XML – activity_main.xml

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/num1"
        android:hint="Enter first number"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <EditText
        android:id="@+id/num2"
        android:hint="Enter second number"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <EditText
        android:id="@+id/num3"
        android:hint="Enter third number"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnFind"
        android:text="Find Largest"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <TextView
        android:id="@+id/txtResult"
        android:textSize="20sp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingTop="12dp" />
</LinearLayout>
```

### 2. Kotlin – MainActivity.kt

```kotlin
package com.example.myapplication

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val button = findViewById<Button>(R.id.btnFind)
        button.setOnClickListener {
            val num1 = findViewById<EditText>(R.id.num1)
            val num2 = findViewById<EditText>(R.id.num2)
            val num3 = findViewById<EditText>(R.id.num3)
            val result = findViewById<TextView>(R.id.txtResult)

            val a = num1.text.toString().toDouble()
            val b = num2.text.toString().toDouble()
            val c = num3.text.toString().toDouble()

            if (a >= b && a >= c) {
                result.text = "Largest = $a"
            } else if (b >= a && b >= c) {
                result.text = "Largest = $b"
            } else {
                result.text = "Largest = $c"
            }
        }
    }
}
```

Sample input: 10, 25, 15  
Expected output: Largest = 25.0

---

<a id="a-q17"></a>
## Q.17 – Pass or Fail with Marks Validation

Accept student marks out of 100 and display Pass or Fail. Accept marks only between 0 and 100.

### 1. XML – activity_main.xml

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/marks"
        android:hint="Enter marks (0 to 100)"
        android:inputType="number"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnCheck"
        android:text="Check Result"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <TextView
        android:id="@+id/txtResult"
        android:textSize="20sp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingTop="12dp" />
</LinearLayout>
```

### 2. Kotlin – MainActivity.kt

```kotlin
package com.example.myapplication

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val button = findViewById<Button>(R.id.btnCheck)
        button.setOnClickListener {
            val marks = findViewById<EditText>(R.id.marks)
            val result = findViewById<TextView>(R.id.txtResult)

            val m = marks.text.toString().toInt()

            if (m < 0 || m > 100) {
                result.text = "Enter marks between 0 and 100"
            } else if (m >= 40) {
                result.text = "Pass"
            } else {
                result.text = "Fail"
            }
        }
    }
}
```

Sample input: 75  
Expected output: Pass (this example uses 40 as the passing mark; follow your college's rule if different)

Passing-mark note: The question paper says Pass or Fail but does not specify the passing threshold. This example uses 40 as a common illustrative threshold. Change 40 if your teacher specifies another value.

---

<a id="a-q18"></a>
## Q.18 – Simple Interest

Accept Principal, Rate and Time and calculate Simple Interest.

### 1. XML – activity_main.xml

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/principal"
        android:hint="Enter principal"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <EditText
        android:id="@+id/rate"
        android:hint="Enter rate"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <EditText
        android:id="@+id/time"
        android:hint="Enter time"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnCalculate"
        android:text="Calculate"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <TextView
        android:id="@+id/txtResult"
        android:textSize="20sp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingTop="12dp" />
</LinearLayout>
```

### 2. Kotlin – MainActivity.kt

```kotlin
package com.example.myapplication

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val button = findViewById<Button>(R.id.btnCalculate)
        button.setOnClickListener {
            val principal = findViewById<EditText>(R.id.principal)
            val rate = findViewById<EditText>(R.id.rate)
            val time = findViewById<EditText>(R.id.time)
            val result = findViewById<TextView>(R.id.txtResult)

            val p = principal.text.toString().toDouble()
            val r = rate.text.toString().toDouble()
            val t = time.text.toString().toDouble()

            val si = (p * r * t) / 100
            result.text = "Simple Interest = $si"
        }
    }
}
```

Sample input: 1000, 5, 2  
Expected output: Simple Interest = 100.0

Formula: Simple Interest = (Principal × Rate × Time) / 100.

---

<a id="a-q19"></a>
## Q.19 – Perimeter of Rectangle

Accept the length and breadth of a rectangle and calculate its perimeter.

### 1. XML – activity_main.xml

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/length"
        android:hint="Enter length"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <EditText
        android:id="@+id/breadth"
        android:hint="Enter breadth"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnCalculate"
        android:text="Calculate"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <TextView
        android:id="@+id/txtResult"
        android:textSize="20sp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingTop="12dp" />
</LinearLayout>
```

### 2. Kotlin – MainActivity.kt

```kotlin
package com.example.myapplication

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val button = findViewById<Button>(R.id.btnCalculate)
        button.setOnClickListener {
            val length = findViewById<EditText>(R.id.length)
            val breadth = findViewById<EditText>(R.id.breadth)
            val result = findViewById<TextView>(R.id.txtResult)

            val l = length.text.toString().toDouble()
            val b = breadth.text.toString().toDouble()

            val perimeter = 2 * (l + b)
            result.text = "Perimeter = $perimeter"
        }
    }
}
```

Sample input: 5, 3  
Expected output: Perimeter = 16.0

---

<a id="a-q20"></a>
## Q.20 – Percentage Calculation

Accept marks obtained and maximum marks and calculate the percentage. Handle maximum marks equal to zero.

### 1. XML – activity_main.xml

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/obtained"
        android:hint="Enter marks obtained"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <EditText
        android:id="@+id/maximum"
        android:hint="Enter maximum marks"
        android:inputType="numberDecimal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/btnCalculate"
        android:text="Calculate"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <TextView
        android:id="@+id/txtResult"
        android:textSize="20sp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:paddingTop="12dp" />
</LinearLayout>
```

### 2. Kotlin – MainActivity.kt

```kotlin
package com.example.myapplication

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val button = findViewById<Button>(R.id.btnCalculate)
        button.setOnClickListener {
            val obtained = findViewById<EditText>(R.id.obtained)
            val maximum = findViewById<EditText>(R.id.maximum)
            val result = findViewById<TextView>(R.id.txtResult)

            val obtainedMarks = obtained.text.toString().toDouble()
            val maximumMarks = maximum.text.toString().toDouble()

            if (maximumMarks == 0.0) {
                result.text = "Maximum marks cannot be zero"
            } else {
                val percentage = (obtainedMarks / maximumMarks) * 100
                result.text = "Percentage = $percentage%"
            }
        }
    }
}
```

Sample input: 80, 100  
Expected output: Percentage = 80.0%

Formula: Percentage = (Marks obtained / Maximum marks) × 100.

---

---

# Set B – Android Mobile Application Development (12 Marks)

**Language:** Kotlin\
**IDE:** Android Studio\
**Layout type:** XML Views\
**Package name used in examples:** `com.example.explicit8`\
Replace the package name with your own project package wherever
required.

## Contents

1. [Q1. Demonstrate Activity Lifecycle: onCreate(), onStart(), onResume() and onDestroy()](#b-q1)
2. [Q2. Demonstrate Activity Lifecycle: onPause(), onStop(), onRestart() and onDestroy()](#b-q2)
3. [Q3. Demonstrate Activity Lifecycle: onCreate(), onStart(), onResume() and onPause()](#b-q3)
4. [Q4. Demonstrate Fragment Lifecycle: onAttach(), onCreate(), onCreateView() and onViewCreated()](#b-q4)
5. [Q5. Demonstrate Fragment Lifecycle: onCreate(), onStart(), onResume() and onPause()](#b-q5)
6. [Q6. Demonstrate Fragment Lifecycle: onCreate(), onStop(), onDestroyView(), onDestroy() and onDetach()](#b-q6)
7. [Q7. Create a Fragment with a welcome TextView and load it using an Activity Button](#b-q7)
8. [Q8. Open Second Activity using an Explicit Intent](#b-q8)
9. [Q9. Pass user's name to Second Activity using Intent Extras](#b-q9)
10. [Q10. Open a website using ACTION_VIEW](#b-q10)
11. [Q11. Open Phone Dialer using ACTION_DIAL](#b-q11)
12. [Q12. Open Email Application using ACTION_SENDTO](#b-q12)
13. [Q13. Perform arithmetic operations on two numbers using buttons](#b-q13)
14. [Q14. Calculate area of square and circle and display both on Second Activity](#b-q14)

## Important setup

-   Create an **Empty Views Activity** project.
-   Use the exact XML file names and view IDs shown below.
-   For Fragment questions, ensure the AndroidX Fragment dependency is
    available.
-   For Questions 8, 9 and 14, create `SecondActivity` using **New →
    Activity → Empty Views Activity**. Android Studio normally adds it
    to `AndroidManifest.xml` automatically.

------------------------------------------------------------------------

<a id="b-q1"></a>
## Q1. Demonstrate Activity Lifecycle: onCreate(), onStart(), onResume() and onDestroy()

### MainActivity.kt

``` kotlin
package com.example.explicit8

import android.os.Bundle
import android.util.Log
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        Log.d("ActivityLife", "onCreate called")
    }

    override fun onStart() {
        super.onStart()
        Log.d("ActivityLife", "onStart called")
    }

    override fun onResume() {
        super.onResume()
        Log.d("ActivityLife", "onResume called")
    }

    override fun onDestroy() {
        super.onDestroy()
        Log.d("ActivityLife", "onDestroy called")
    }
}
```

**Output:** Open Logcat and filter by `ActivityLife`. The four lifecycle
messages appear when their callbacks run. Press Back to finish the
Activity and observe `onDestroy()`.

------------------------------------------------------------------------

<a id="b-q2"></a>
## Q2. Demonstrate Activity Lifecycle: onPause(), onStop(), onRestart() and onDestroy()

### MainActivity.kt

``` kotlin
package com.example.explicit8

import android.os.Bundle
import android.util.Log
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
    }

    override fun onPause() {
        super.onPause()
        Log.d("ActivityLife", "onPause called")
    }

    override fun onStop() {
        super.onStop()
        Log.d("ActivityLife", "onStop called")
    }

    override fun onRestart() {
        super.onRestart()
        Log.d("ActivityLife", "onRestart called")
    }

    override fun onDestroy() {
        super.onDestroy()
        Log.d("ActivityLife", "onDestroy called")
    }
}
```

**Output:** Press Home to move the Activity to the background; observe
`onPause()` and `onStop()`. Reopen the app to observe `onRestart()`.
Press Back to finish it and observe `onDestroy()`.

------------------------------------------------------------------------

<a id="b-q3"></a>
## Q3. Demonstrate Activity Lifecycle: onCreate(), onStart(), onResume() and onPause()

### MainActivity.kt

``` kotlin
package com.example.explicit8

import android.os.Bundle
import android.util.Log
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        Log.d("ActivityLife", "onCreate called")
    }

    override fun onStart() {
        super.onStart()
        Log.d("ActivityLife", "onStart called")
    }

    override fun onResume() {
        super.onResume()
        Log.d("ActivityLife", "onResume called")
    }

    override fun onPause() {
        super.onPause()
        Log.d("ActivityLife", "onPause called")
    }
}
```

**Output:** Launch the app and check Logcat. Press Home or open another
screen to trigger `onPause()`.

------------------------------------------------------------------------

<a id="b-q4"></a>
## Q4. Demonstrate Fragment Lifecycle: onAttach(), onCreate(), onCreateView() and onViewCreated()

Create `MyFragment.kt` and `fragment_my.xml`.

### fragment_my.xml

``` xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Fragment Lifecycle"
        android:textSize="24sp" />
</LinearLayout>
```

### MyFragment.kt

``` kotlin
package com.example.explicit8

import android.content.Context
import android.os.Bundle
import android.util.Log
import android.view.LayoutInflater
import android.view.View
import android.view.ViewGroup
import androidx.fragment.app.Fragment

class MyFragment : Fragment() {
    override fun onAttach(context: Context) {
        super.onAttach(context)
        Log.d("FragmentLife", "onAttach called")
    }

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        Log.d("FragmentLife", "onCreate called")
    }

    override fun onCreateView(
        inflater: LayoutInflater,
        container: ViewGroup?,
        savedInstanceState: Bundle?
    ): View {
        Log.d("FragmentLife", "onCreateView called")
        return inflater.inflate(R.layout.fragment_my, container, false)
    }

    override fun onViewCreated(view: View, savedInstanceState: Bundle?) {
        super.onViewCreated(view, savedInstanceState)
        Log.d("FragmentLife", "onViewCreated called")
    }
}
```

### activity_main.xml

``` xml
<?xml version="1.0" encoding="utf-8"?>
<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/fragmentContainer"
    android:layout_width="match_parent"
    android:layout_height="match_parent" />
```

### MainActivity.kt

``` kotlin
package com.example.explicit8

import android.os.Bundle
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        if (savedInstanceState == null) {
            supportFragmentManager.beginTransaction()
                .replace(R.id.fragmentContainer, MyFragment())
                .commit()
        }
    }
}
```

**Output:** Check Logcat using the tag `FragmentLife` to see the four
callbacks.

------------------------------------------------------------------------

<a id="b-q5"></a>
## Q5. Demonstrate Fragment Lifecycle: onCreate(), onStart(), onResume() and onPause()

Use the same `activity_main.xml`, `fragment_my.xml`, and
`MainActivity.kt` from Q4.

### MyFragment.kt

``` kotlin
package com.example.explicit8

import android.os.Bundle
import android.util.Log
import android.view.LayoutInflater
import android.view.View
import android.view.ViewGroup
import androidx.fragment.app.Fragment

class MyFragment : Fragment() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        Log.d("FragmentLife", "onCreate called")
    }

    override fun onCreateView(
        inflater: LayoutInflater,
        container: ViewGroup?,
        savedInstanceState: Bundle?
    ): View {
        return inflater.inflate(R.layout.fragment_my, container, false)
    }

    override fun onStart() {
        super.onStart()
        Log.d("FragmentLife", "onStart called")
    }

    override fun onResume() {
        super.onResume()
        Log.d("FragmentLife", "onResume called")
    }

    override fun onPause() {
        super.onPause()
        Log.d("FragmentLife", "onPause called")
    }
}
```

**Output:** Check Logcat with tag `FragmentLife`. The callbacks are
displayed as the Fragment starts and loses focus.

------------------------------------------------------------------------

<a id="b-q6"></a>
## Q6. Demonstrate Fragment Lifecycle: onCreate(), onStop(), onDestroyView(), onDestroy() and onDetach()

Use `fragment_my.xml` from Q4.

### activity_main.xml

``` xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <Button
        android:id="@+id/btnRemove"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Remove Fragment" />

    <FrameLayout
        android:id="@+id/fragmentContainer"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />
</LinearLayout>
```

### MyFragment.kt

``` kotlin
package com.example.explicit8

import android.os.Bundle
import android.util.Log
import android.view.LayoutInflater
import android.view.View
import android.view.ViewGroup
import androidx.fragment.app.Fragment

class MyFragment : Fragment() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        Log.d("FragmentLife", "onCreate called")
    }

    override fun onCreateView(
        inflater: LayoutInflater,
        container: ViewGroup?,
        savedInstanceState: Bundle?
    ): View {
        return inflater.inflate(R.layout.fragment_my, container, false)
    }

    override fun onStop() {
        super.onStop()
        Log.d("FragmentLife", "onStop called")
    }

    override fun onDestroyView() {
        super.onDestroyView()
        Log.d("FragmentLife", "onDestroyView called")
    }

    override fun onDestroy() {
        super.onDestroy()
        Log.d("FragmentLife", "onDestroy called")
    }

    override fun onDetach() {
        super.onDetach()
        Log.d("FragmentLife", "onDetach called")
    }
}
```

### MainActivity.kt

``` kotlin
package com.example.explicit8

import android.os.Bundle
import android.widget.Button
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        if (savedInstanceState == null) {
            supportFragmentManager.beginTransaction()
                .replace(R.id.fragmentContainer, MyFragment())
                .commit()
        }

        findViewById<Button>(R.id.btnRemove).setOnClickListener {
            val fragment = supportFragmentManager.findFragmentById(R.id.fragmentContainer)
            if (fragment != null) {
                supportFragmentManager.beginTransaction()
                    .remove(fragment)
                    .commit()
            }
        }
    }
}
```

**Output:** Tap **Remove Fragment** and check Logcat using
`FragmentLife` for the destruction callbacks.

------------------------------------------------------------------------

<a id="b-q7"></a>
## Q7. Create a Fragment with a welcome TextView and load it using an Activity Button

### activity_main.xml

``` xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <Button
        android:id="@+id/btnLoad"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Load Fragment" />

    <FrameLayout
        android:id="@+id/fragmentContainer"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />
</LinearLayout>
```

### fragment_welcome.xml

``` xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Welcome to Fragment!"
        android:textSize="24sp" />
</LinearLayout>
```

### WelcomeFragment.kt

``` kotlin
package com.example.explicit8

import android.os.Bundle
import android.view.LayoutInflater
import android.view.View
import android.view.ViewGroup
import androidx.fragment.app.Fragment

class WelcomeFragment : Fragment() {
    override fun onCreateView(
        inflater: LayoutInflater,
        container: ViewGroup?,
        savedInstanceState: Bundle?
    ): View {
        return inflater.inflate(R.layout.fragment_welcome, container, false)
    }
}
```

### MainActivity.kt

``` kotlin
package com.example.explicit8

import android.os.Bundle
import android.widget.Button
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        findViewById<Button>(R.id.btnLoad).setOnClickListener {
            supportFragmentManager.beginTransaction()
                .replace(R.id.fragmentContainer, WelcomeFragment())
                .commit()
        }
    }
}
```

**Output:** Tap **Load Fragment** to display "Welcome to Fragment!"

------------------------------------------------------------------------

<a id="b-q8"></a>
## Q8. Open Second Activity using an Explicit Intent

### activity_main.xml

``` xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical">

    <Button
        android:id="@+id/btnOpen"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Open Second Activity" />
</LinearLayout>
```

### MainActivity.kt

``` kotlin
package com.example.explicit8

import android.content.Intent
import android.os.Bundle
import android.widget.Button
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        findViewById<Button>(R.id.btnOpen).setOnClickListener {
            val intent = Intent(this, SecondActivity::class.java)
            startActivity(intent)
        }
    }
}
```

### activity_second.xml

``` xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Welcome to Second Activity!"
        android:textSize="24sp" />
</LinearLayout>
```

### SecondActivity.kt

``` kotlin
package com.example.explicit8

import android.os.Bundle
import androidx.appcompat.app.AppCompatActivity

class SecondActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_second)
    }
}
```

**Output:** Tap the button in MainActivity. SecondActivity opens and
displays the welcome message.

------------------------------------------------------------------------

<a id="b-q9"></a>
## Q9. Pass user's name to Second Activity using Intent Extras

### activity_main.xml

``` xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/etName"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter your name"
        android:inputType="textPersonName" />

    <Button
        android:id="@+id/btnSubmit"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Send" />
</LinearLayout>
```

### MainActivity.kt

``` kotlin
package com.example.explicit8

import android.content.Intent
import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val etName = findViewById<EditText>(R.id.etName)
        val btnSubmit = findViewById<Button>(R.id.btnSubmit)

        btnSubmit.setOnClickListener {
            val name = etName.text.toString()
            val intent = Intent(this, SecondActivity::class.java)
            intent.putExtra("USER_NAME", name)
            startActivity(intent)
        }
    }
}
```

### activity_second.xml

``` xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical">

    <TextView
        android:id="@+id/tvWelcome"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textSize="24sp" />
</LinearLayout>
```

### SecondActivity.kt

``` kotlin
package com.example.explicit8

import android.os.Bundle
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class SecondActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_second)

        val name = intent.getStringExtra("USER_NAME")
        findViewById<TextView>(R.id.tvWelcome).text = "Welcome, $name!"
    }
}
```

**Output:** Enter a name, tap Send, and the second screen displays
`Welcome, [entered name]!`.

------------------------------------------------------------------------

<a id="b-q10"></a>
## Q10. Open a website using ACTION_VIEW

### activity_main.xml

``` xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/etUrl"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter website URL"
        android:inputType="textUri" />

    <Button
        android:id="@+id/btnOpen"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Open Website" />
</LinearLayout>
```

### MainActivity.kt

``` kotlin
package com.example.explicit8

import android.content.Intent
import android.net.Uri
import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val etUrl = findViewById<EditText>(R.id.etUrl)
        findViewById<Button>(R.id.btnOpen).setOnClickListener {
            var url = etUrl.text.toString().trim()
            if (url.isNotEmpty()) {
                if (!url.startsWith("http://") && !url.startsWith("https://")) {
                    url = "https://$url"
                }
                val intent = Intent(Intent.ACTION_VIEW, Uri.parse(url))
                startActivity(intent)
            }
        }
    }
}
```

**Output:** Enter a website address and tap Open Website. Android opens
it in an available browser.

------------------------------------------------------------------------

<a id="b-q11"></a>
## Q11. Open Phone Dialer using ACTION_DIAL

### activity_main.xml

``` xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/etNumber"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter mobile number"
        android:inputType="phone" />

    <Button
        android:id="@+id/btnCall"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Call" />
</LinearLayout>
```

### MainActivity.kt

``` kotlin
package com.example.explicit8

import android.content.Intent
import android.net.Uri
import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val etNumber = findViewById<EditText>(R.id.etNumber)
        findViewById<Button>(R.id.btnCall).setOnClickListener {
            val number = etNumber.text.toString().trim()
            if (number.isNotEmpty()) {
                val intent = Intent(Intent.ACTION_DIAL, Uri.parse("tel:$number"))
                startActivity(intent)
            }
        }
    }
}
```

**Output:** Enter a number and tap Call. The phone dialer opens with the
number filled in. `ACTION_DIAL` does not place the call directly.

------------------------------------------------------------------------

<a id="b-q12"></a>
## Q12. Open Email Application using ACTION_SENDTO

### activity_main.xml

``` xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/etEmail"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter email address"
        android:inputType="textEmailAddress" />

    <Button
        android:id="@+id/btnEmail"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Send Email" />
</LinearLayout>
```

### MainActivity.kt

``` kotlin
package com.example.explicit8

import android.content.Intent
import android.net.Uri
import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val etEmail = findViewById<EditText>(R.id.etEmail)
        findViewById<Button>(R.id.btnEmail).setOnClickListener {
            val email = etEmail.text.toString().trim()
            if (email.isNotEmpty()) {
                val intent = Intent(Intent.ACTION_SENDTO)
                intent.data = Uri.parse("mailto:$email")
                startActivity(intent)
            }
        }
    }
}
```

**Output:** Enter an email address and tap Send Email. An available
email application opens with the recipient filled in.

------------------------------------------------------------------------

<a id="b-q13"></a>
## Q13. Perform arithmetic operations on two numbers using buttons

### activity_main.xml

``` xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    android:padding="16dp">

    <EditText
        android:id="@+id/etNum1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter first number"
        android:inputType="numberDecimal|numberSigned" />

    <EditText
        android:id="@+id/etNum2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter second number"
        android:inputType="numberDecimal|numberSigned" />

    <Button
        android:id="@+id/btnAdd"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Addition" />

    <Button
        android:id="@+id/btnSub"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Subtraction" />

    <Button
        android:id="@+id/btnMul"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Multiplication" />

    <Button
        android:id="@+id/btnDiv"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Division" />

    <TextView
        android:id="@+id/tvResult"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Result"
        android:textSize="22sp" />
</LinearLayout>
```

### MainActivity.kt

``` kotlin
package com.example.explicit8

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val num1 = findViewById<EditText>(R.id.etNum1)
        val num2 = findViewById<EditText>(R.id.etNum2)
        val result = findViewById<TextView>(R.id.tvResult)

        fun getNumbers(): Pair<Double, Double>? {
            val a = num1.text.toString().toDoubleOrNull()
            val b = num2.text.toString().toDoubleOrNull()
            if (a == null || b == null) {
                result.text = "Enter valid numbers"
                return null
            }
            return Pair(a, b)
        }

        findViewById<Button>(R.id.btnAdd).setOnClickListener {
            val values = getNumbers()
            if (values != null) result.text = "Result: ${values.first + values.second}"
        }

        findViewById<Button>(R.id.btnSub).setOnClickListener {
            val values = getNumbers()
            if (values != null) result.text = "Result: ${values.first - values.second}"
        }

        findViewById<Button>(R.id.btnMul).setOnClickListener {
            val values = getNumbers()
            if (values != null) result.text = "Result: ${values.first * values.second}"
        }

        findViewById<Button>(R.id.btnDiv).setOnClickListener {
            val values = getNumbers()
            if (values != null) {
                if (values.second == 0.0) {
                    result.text = "Cannot divide by zero"
                } else {
                    result.text = "Result: ${values.first / values.second}"
                }
            }
        }
    }
}
```

**Output:** Enter two numbers and tap the required operation button. The
result appears below the buttons.

------------------------------------------------------------------------

<a id="b-q14"></a>
## Q14. Calculate area of square and circle and display both on Second Activity

### activity_main.xml

``` xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/etSide"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter side of square"
        android:inputType="numberDecimal" />

    <EditText
        android:id="@+id/etRadius"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter radius of circle"
        android:inputType="numberDecimal" />

    <Button
        android:id="@+id/btnCalculate"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Calculate Areas" />
</LinearLayout>
```

### MainActivity.kt

``` kotlin
package com.example.explicit8

import android.content.Intent
import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val etSide = findViewById<EditText>(R.id.etSide)
        val etRadius = findViewById<EditText>(R.id.etRadius)

        findViewById<Button>(R.id.btnCalculate).setOnClickListener {
            val side = etSide.text.toString().toDoubleOrNull()
            val radius = etRadius.text.toString().toDoubleOrNull()

            if (side != null && radius != null) {
                val squareArea = side * side
                val circleArea = 3.14 * radius * radius

                val intent = Intent(this, SecondActivity::class.java)
                intent.putExtra("SQUARE_AREA", squareArea)
                intent.putExtra("CIRCLE_AREA", circleArea)
                startActivity(intent)
            }
        }
    }
}
```

### activity_second.xml

``` xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical">

    <TextView
        android:id="@+id/tvResult"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textSize="22sp" />
</LinearLayout>
```

### SecondActivity.kt

``` kotlin
package com.example.explicit8

import android.os.Bundle
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class SecondActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_second)

        val squareArea = intent.getDoubleExtra("SQUARE_AREA", 0.0)
        val circleArea = intent.getDoubleExtra("CIRCLE_AREA", 0.0)

        findViewById<TextView>(R.id.tvResult).text =
            "Area of Square = $squareArea\nArea of Circle = $circleArea"
    }
}
```

**Output:** Enter the square's side and circle's radius. Tap Calculate
Areas. The second Activity displays both calculated areas.

------------------------------------------------------------------------

## Final checklist

-   Keep the package declaration the same as your Android Studio project
    package.
-   XML IDs must match the IDs used in Kotlin.
-   Use the correct layout resource name in `setContentView()`.
-   For lifecycle questions, view messages in Logcat using the tag
    `ActivityLife` or `FragmentLife`.
-   For Questions 8, 9 and 14, ensure `SecondActivity` exists in the
    project and is declared in `AndroidManifest.xml` (Android Studio
    usually adds it automatically).
