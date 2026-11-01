# SINGRE Android — compilation APK sans Android Studio

Ce projet Android ouvre l'instance web SINGRE à l'adresse configurée dans `app/src/main/java/bf/singre/mobile/MainActivity.java`.

## Obtenir l'APK avec GitHub Actions (sans Android Studio)

1. Décompresser le ZIP.
2. Créer un dépôt GitHub (par exemple `SINGRE-Android`).
3. Envoyer **le contenu du dossier `SINGRE_Android`** à la racine du dépôt. Le dossier `.github/workflows/build-apk.yml` doit être conservé.
4. Dans GitHub, ouvrir l'onglet **Actions**. Si GitHub demande d'autoriser les workflows, accepter.
5. Le workflow démarre automatiquement après l'envoi sur `main` ou `master`. On peut aussi le lancer avec **Actions > Build SINGRE APK > Run workflow**.
6. Ouvrir l'exécution terminée, descendre à **Artifacts**, puis télécharger `SINGRE-debug-APK`.
7. Décompresser l'archive téléchargée : le fichier à installer est `app-debug.apk`.

## Important
- Le projet est une enveloppe Android WebView : il affiche le serveur web SINGRE, il n'intègre pas encore une vraie collecte hors ligne.
- Le serveur `https://singre-guiriko.onrender.com` doit répondre correctement. L'erreur Render `TemplateNotFound: login.html` signalée précédemment doit être corrigée avant les tests fonctionnels.
- Il s'agit d'un APK **debug** pour essais. Pour une diffusion officielle, il faudra générer un APK signé de release et protéger la clé de signature.
