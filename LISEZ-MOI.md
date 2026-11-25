# Plan Terrain – vraie application Android / iOS (Capacitor)

## ANDROID – la méthode la plus simple (sans rien installer sur PC)
1. Créez un compte gratuit sur github.com, puis « New repository » (nom : plan-terrain).
2. « uploading an existing file » : glissez TOUT le contenu de ce dossier (y compris le dossier .github).
   Si .github n'est pas pris : « Add file > Create new file », nom `.github/workflows/android.yml`, collez le contenu du fichier.
3. Onglet **Actions** > « Build Android APK » > **Run workflow**. Attendez ~5 min.
4. Cliquez sur l'exécution terminée > en bas **plan-terrain-apk** (zip) > téléchargez.
5. Dézippez, envoyez `app-debug.apk` sur le téléphone, ouvrez-le (autorisez « sources inconnues »). L'application s'installe.

## ANDROID – sur votre ordinateur
Installez Node.js 20 et Android Studio, puis :
    npm install
    npx cap add android
    npx cap sync android
    npx cap open android      (Android Studio : Build > Build APK)

## iOS (iPhone) – il faut obligatoirement un Mac avec Xcode
    npm install
    npx cap add ios
    npx cap sync ios
    npx cap open ios          (Xcode : choisir votre « Team », brancher l'iPhone, bouton Run)
- Compte Apple gratuit : l'app reste 7 jours sur votre iPhone.
- App Store / TestFlight : compte Apple Developer (99 $/an).

## Publier sur Google Play
Compte Google Play (25 $ une fois) + build « release » signé (Android Studio : Build > Generate Signed Bundle).

## Modifier l'application
Tout le programme est dans `www/index.html`. Après modification : `npx cap sync`.

## Fonctions de l'application
- Fonctionne 100 % hors connexion.
- 📁 Projets : enregistrer, ouvrir, supprimer plusieurs terrains (dans le téléphone).
- 📤 Partager : envoie le plan + la légende en image (WhatsApp, e-mail, etc.).
