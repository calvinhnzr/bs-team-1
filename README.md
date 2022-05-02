# Praktikum

## Aufgabe 1 a)
- adb: android debug bridge
- adb shell: öffnet terminal des Smartphones
- adb devices: zeigt Geräte an
- adb push/pull: Datentransfer zwischen Smartphone und Android Studio

## Aufgabe 1 b)
- /adb shell
- /top: zeigt alle aktiven Prozesse an
- /ps -A: zeigt alle Prozesse an
- /ps -e: zeigt alle Prozesse an
- /ps -p $PID: zeigt einen bestimmmten Prozess an
- /ps --pid $PID: zeigt einen bestimmmten Prozess an
- /ps --ppid $PPID: zeigt Child Prozesse von Parent
- /ps -A -l: zeigt prio in Nice an

## Aufgabe 1 c)

```MainActivity.kt```
```kotlin
package com.example.bs_hello_world

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
// import var type
import android.widget.TextView
//
import android.os.Process


class MainActivity : AppCompatActivity() {

    // spätere initialisierung
    // legt variable von typo TextView an
    private lateinit var view: TextView


    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        // connect var with element from canvas; R = res
        view = findViewById(R.id.PID)
        // save process id to val
        val id = Process.myPid()
        // write pid in text element
        view.text = "PID: ${id.toString()}"
    }
}
```

```activity_main.xml```
```xml
<TextView
        android:id="@+id/PID"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="TextView"
        android:textAllCaps="true"
        android:textSize="30sp"
        tools:layout_editor_absoluteX="176dp"
        tools:layout_editor_absoluteY="489dp" />

```
