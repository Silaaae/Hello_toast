: L'application HelloToast a été développée dans le cadre d'un TP Android avec Android Studio.
L'application HelloToast a été développée dans le cadre d'un TP Android avec Android Studio. L'objectif était de créer une application simple comportant deux boutons : un affichant un message Toast et un autre incrémentant un compteur à l'écran.
Étape 1 — Création du projet
Le projet a été créé dans Android Studio en sélectionnant New Project → Empty Activity, avec le nom HelloToast, le langage Java et une API minimum de 24 (Android 7.0).
Étape 2 — Interface XML
Le fichier activity_main.xml a été configuré avec un LinearLayout vertical centré contenant un TextView pour le compteur et deux Button. Une erreur de compilation a été rencontrée : le namespace xmlns:android était absent de la balise racine, provoquant un ParseError. Les attributs layout_width et layout_height manquaient également sur chaque composant. Ces deux points ont été corrigés.
Étape 3 — Logique Java
Le fichier MainActivity.java présentait 21 erreurs dues à des imports manquants et à l'absence de la déclaration de package. Après correction, les deux boutons ont été reliés à leurs actions via setOnClickListener : le premier appelle Toast.makeText() et le second incrémente une variable count puis met à jour le TextView via setText().
Problèmes rencontrés
L'émulateur MobSF_DIVA_API_30 était bloqué en tant que processus Windows (PID 28544). La commande kill -9 ne fonctionnant pas sous PowerShell, la solution a été Stop-Process -Id 28544 -Force suivi de la suppression du fichier .lock de l'AVD.
Résultat
L'application fonctionne correctement sur l'émulateur Android 11. Le bouton TOAST affiche le message "Bonjour !" et le bouton COUNT incrémente le compteur affiché à l'écran.
<img width="276" height="570" alt="image" src="https://github.com/user-attachments/assets/80e8bf15-e554-4499-ad7f-def75ad974e2" />
