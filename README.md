<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/fondo_cocina">

    <TextView
        android:id="@+id/txtPiso"
        android:text="Segundo Piso"
        android:textSize="22sp"
        android:textStyle="bold"
        android:textColor="#FFFFFF"
        android:layout_marginTop="24dp"
        android:layout_centerHorizontal="true"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />

    <ImageButton
        android:id="@+id/btnFoco"
        android:layout_width="150dp"
        android:layout_height="150dp"
        android:src="@drawable/foco_off"
        android:layout_centerHorizontal="true"
        android:layout_below="@id/txtPiso"
        android:layout_marginTop="40dp"
        android:contentDescription="Foco" />

    <ImageButton
        android:id="@+id/btnEnchufe"
        android:layout_width="150dp"
        android:layout_height="150dp"
        android:src="@drawable/enchufe_off"
        android:layout_centerHorizontal="true"
        android:layout_below="@id/btnFoco"
        android:layout_marginTop="30dp"
        android:contentDescription="Enchufe" />

</RelativeLayout>

package com.tu_paquete;

import android.os.Bundle;
import android.view.View;
import android.widget.ImageButton;
import androidx.appcompat.app.AppCompatActivity;

public class SegundoPisoActivity extends AppCompatActivity {

    ImageButton btnFoco, btnEnchufe;
    boolean focoEncendido = false;
    boolean enchufeEncendido = false;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_segundo_piso);

        btnFoco = findViewById(R.id.btnFoco);
        btnEnchufe = findViewById(R.id.btnEnchufe);

        btnFoco.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                focoEncendido = !focoEncendido;
                btnFoco.setImageResource(focoEncendido ? R.drawable.foco_on : R.drawable.foco_off);
            }
        });

        btnEnchufe.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                enchufeEncendido = !enchufeEncendido;
                btnEnchufe.setImageResource(enchufeEncendido ? R.drawable.enchufe_on : R.drawable.enchufe_off);
            }
        });
    }
}
