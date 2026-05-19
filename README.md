Rapport de TP — Application Android HelloToast

Informations générales

Nom : NISRINE
Date : 19 mai 2026
IDE : Android Studio
Langage : Java
API minimum : 24 (Android 7.0)
Émulateur : MobSF_DIVA_API_30 (Android 11)
Dépôt GitHub : https://github.com/Silaaae/Hello_toast


Objectif
Créer une application Android simple comportant deux boutons : l'un affiche un message Toast, l'autre incrémente un compteur affiché à l'écran.

Étape 1 — Création du projet
Ouverture d'Android Studio, sélection de New Project → Empty Activity. Nom du projet : HelloToast, langage Java, API minimum 24.

Étape 2 — Interface (activity_main.xml)
xml<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="16dp">

    <TextView
        android:id="@+id/text_count"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="0"
        android:textSize="36sp"
        android:layout_marginBottom="24dp" />

    <Button
        android:id="@+id/button_toast"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Afficher un message"
        android:layout_marginBottom="12dp" />

    <Button
        android:id="@+id/button_count"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Incrémenter le compteur" />

</LinearLayout>

Étape 3 — Logique Java (MainActivity.java)
javapackage com.example.hello_toastt;

import android.os.Bundle;
import android.widget.Button;
import android.widget.TextView;
import android.widget.Toast;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    private int count = 0;
    private TextView textCount;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        textCount = findViewById(R.id.text_count);
        Button buttonToast = findViewById(R.id.button_toast);
        Button buttonCount = findViewById(R.id.button_count);

        buttonToast.setOnClickListener(v -> {
            Toast.makeText(this, "Bonjour !", Toast.LENGTH_SHORT).show();
        });

        buttonCount.setOnClickListener(v -> {
            count++;
            textCount.setText(String.valueOf(count));
        });
    }
}

Problèmes rencontrés

21 erreurs Java — imports et déclaration de package manquants. Corrigé en ajoutant le package et tous les imports nécessaires.
ParseError XML — namespace xmlns:android absent de la balise racine, et attributs layout_width / layout_height manquants sur chaque composant. Corrigé en restructurant le fichier XML.
Émulateur bloqué (PID 28544) — la commande kill -9 ne fonctionne pas sous PowerShell. Corrigé avec Stop-Process -Id 28544 -Force puis suppression du fichier .lock.


Résultat
L'application fonctionne correctement sur l'émulateur Android 11. Le bouton TOAST affiche "Bonjour !" et le bouton COUNT incrémente le compteur affiché à l'écran. Le code source a été poussé sur GitHub avec succès.
<img width="276" height="570" alt="image" src="https://github.com/user-attachments/assets/80e8bf15-e554-4499-ad7f-def75ad974e2" />
