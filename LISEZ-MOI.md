# BioMaint IA – projet APK (Android)

## Option A – Générer l'APK sans Android Studio (GitHub)
1. Crée un compte et un dépôt GitHub (branche `main`).
2. Envoie tout le contenu de ce dossier dans le dépôt (y compris `.github/workflows/apk.yml`).
3. Onglet **Actions** > **Build APK** > **Run workflow**.
4. Quand c'est terminé (5 à 10 min), ouvre l'exécution et télécharge **BioMaint-IA-apk** : il contient `app-debug.apk`.
5. Copie l'APK sur le téléphone et installe-le (autoriser les sources inconnues).

## Option B – Sur PC avec Android Studio
1. Installer Node.js 20, JDK 17 et Android Studio.
2. Dans ce dossier : `npm install`, `npx cap add android`
3. Dans `android/app/src/main/AndroidManifest.xml`, ajouter avant `</manifest>` :
   `<uses-permission android:name="android.permission.POST_NOTIFICATIONS"/>`
   `<uses-permission android:name="android.permission.RECEIVE_BOOT_COMPLETED"/>`
4. `npx cap sync android` puis `npx cap open android`, et Build > Build APK(s).

## Utilisation
- Réglages : coller la clé API Gemini (Google AI Studio, gratuite) et choisir la langue.
- En ligne : fiche équipement > Rechercher / Traduire le manuel.
- Hors ligne : ajouter des équipements et planifier des maintenances. Les recherches demandées sont mises en attente et relancées à la reconnexion.
- Notifications : J-7, J-3, J-1, jour J, puis rappel quotidien à 8 h tant que la maintenance est en retard.
- Les textes générés par l'IA doivent être vérifiés avec la documentation du constructeur.
